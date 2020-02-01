## Gormの`Opne`関数で、DBのポートを接続するときの方法

> `db,err := gorm.Open("mysql", "docker_user:docker_user_pwd@tcp(docker.for.mac.localhost:3306)/docker_db")`

の`docker.for.mac.localhost`のように書く。

詳細は[こちら](https://qiita.com/Asayu123/items/ccfe4ccfc417ce57f445)のリンクに記載.

