# Go基本

## パッケージとは
Goでは、すべてのプログラムはパッケージに所属している。
そのパッケージには、原則が存在する。

1. 1つのファイルに複数のパッケージを設定してはならない。
2. 1つのディレクトリに複数のパッケージをおいてはならない
3. package mainにあるmain関数がエンドポイントとされている（ここから処理が始まる）

## import とは
読み込む必要のあるパッケージを宣言するところ。


## プログラムを実行する
### `go build`
Goはコンパイル型言語なので、コンパイルする必要がある。

```
go build [コンパイル後のファイル名] [コンパイルしたいファイル名]
```

オプションなしで`go build`を叩くと、自動的にmainパッケージを読み込み、main関数があるファイルを特定し、そのファイル名を使ったバイナリファイルが生成される。

### `go run`
`go build`はコンパイルのみを行うが、`go run`は、コンパイルから実行までしてくれるコマンド。

注意点として、`go build`はカレントディレクトリ以下すべてのファイルを読み込んでくれる。が、`go run`は指定したファイルのみを読み込み・実行する。


## Dockerを使用した場合
1. dockerファイルをビルドする
`$ docker-compose build --no-cache`
※ `--no-cache`は、キャッシュされたイメージを再利用しないようにするため

2. ビルドされたイメージを実行する
`$ docker-comopse up -d`
※ `-d`オプションは、バックグランドで実行するためのオプション

3. ビルドしたコンテナ内で、`go run main.go`する。
実現方法が主に3種類ある。

a. Dockerfileに定義する方法

下記の設定を定義する。

```
CMD ["go", "run", "main.go"]
```


b. dockerコマンドから実行する方法

シェルから下記のdockerの実行コマンドを実行する

```
docker exec -it blog_app go run main.go
```


c. 作成されたイメージの中で、実行する方法 

まず、作成されたイメージの中に入る

```
docker exec -it blog_app /bin/sh
```

Golangのビルド&実行コマンドをたたく

```
go run main.go
```


## 参考文献
- [go run と go buildの違い](http://nununu.hatenablog.jp/entry/2016/09/20/210000)
- [他言語プログラマがgolangの基本を押さえる為のまとめ](https://qiita.com/tfrcm/items/e2a3d7ce7ab8868e37f7)
- [他言語から来た人がGoを使い始めてすぐハマったこととその答え](https://qiita.com/mumoshu/items/0d2f2a13c6e9fc8da2a4)

