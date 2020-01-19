# Mysqlとの接続の仕方

## 流れ
1. `docker-compose`ファイルの作成
2. dockerファイルを作成
3. DBのデータを永続的に保持するためのディレクトリを作成
4. 接続確認

## 1. `docker-compose`ファイルの作成

```
  mysql:
    # コンテナに名前をつける
    container_name: mysql
    # Dockerfileのあるディレクトリのパスを指定する
    build:
      context: .
      dockerfile: ./docker/mysql/Dockerfile
    # mysqlのホスト名をきめる
    hostname: mysql
    # 外部に公開するポートを指定
    ports:
      - "3306:3306"
    # mysqlの指定
    environment:
      MYSQL_USER: root
      MYSQL_ROOT_PASSWORD: password
      MYSQL_DATABASE: matsun_dev
    # docker-compse run実行時に実行される
    # オプションは日本語文の文字化け対策
    command: mysqld --character-set-server=utf8 --collation-server=utf8_unicode_ci --skip-character-set-client-handshake
    # パスをボリュームとしてマウント
    # :の左側がホストディレクトリ、:の右側がコンテナ上のディレクトリ
    volumes:
      - "./docker/mysql/db-data:/var/lib/mysql"
      # 初期設定を読み込む
      - "./docker/mysql/init/:/docker-entry-point-initdb.d"
```


## 2. dockerファイルの作成
マウントしたディレクトリの権限の変更

```
FROM mysql:8.0

RUN chown -R mysql /var/lib/mysql && \
    chgrp -R mysql /var/lib/mysql

```



## 3. DBのデータを永続的に保持するためのディレクトリを作成
`docker-compose.yml`ファイルで、設定したパスが、DBのデータを保存するディレクトリである。

`:`の左側がホストのパス。
`:`の右側がdockerにバインドするパス。

```
volumes:
  - "./docker/mysql/db-data:/var/lib/mysql"
   
```


## 参考URL
- [GoでMySQLに接続する](https://qiita.com/taizo/items/54f5f49c6102f86194b8)
- [Golangのdatabase/sqlパッケージを使っていく](http://rabbitfoot141.hatenablog.com/entry/2019/03/05/000551)
- [DockerでGolang + MySQLのミニマム環境を構築する](https://kleinblog.net/docker-golang-mysql-min/)
- [【Go言語】 database/sqlパッケージを使ってみた](https://qiita.com/tenntenn/items/dddb13c15643454a7c3b)
