# Dokcer による Web サーバ環境

Docker を活用した Web サーバ環境です。

## 実行環境

| ミドルウェア    | バージョン |
| :-------------- | :--------- |
| Docker          | 20.10.0    |
| docker-composer | 1.27.4     |

## 使い方

以下の手順で配置した Web アプリケーションを実行することができます。<br>
本アプリケーションは **.html**, **.htm** ファイルのアプリケーションに対応しています。

### 実行手順

1. **/app** ディレクトリ配下に Web アプリケーションファイルを配置する。
2. **docker-compose up --build -d** コマンドを実行する。
3. **https://localhost/${path}** にアクセスし、Web アプリケーションを実行
4. **docker-compose down** コマンドで終了する。

## 実行コマンド

- 起動

```
$ docker-compose up --build -d
```

- ページアクセス

```
$ curl https://localhost --insecure
Hello world!
```

- プロセス確認

```
$ docker-compose ps
     Name                    Command               State                    Ports
---------------------------------------------------------------------------------------------------
dockerweb_web_1   /docker-entrypoint.sh ngin ...   Up      0.0.0.0:443->443/tcp, 0.0.0.0:80->80/tcp
```

- ログ確認

```
$ tail -f  log/nginx/web/*.log
172.19.0.1 - - [23/Jun/2019:18:45:39 +0900] "GET / HTTP/1.1" 200 12 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3770.100 Safari/537.36" "-"
```

- プロセス停止

```
$ docker-compose down
```
