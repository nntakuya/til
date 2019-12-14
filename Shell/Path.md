# Pathを通すとは、環境変数とは

## Pathを通すとは
コマンドが格納されているPathを登録すること

下記の2つのコードが同じ動きをする
ex)
```
$ pwd

$ /bin/pwd

```

※ [binディレクトリについて](https://qiita.com/totzyuta/items/84d610f56129a186f0c5)


## Pathの設定・追加
exportコマンドを利用する。

例えば、Pathに`/xxx/bin`を追加したい場合
```
$ export PATH=/xxx/bin:$PATH
```
のようにする。


ここで注意したいのは、`$PATH`を書いていない場合、PATHが`/xxx/bin`のみになってしまう。


## PATHの取り消し
PATHをすべて消したい場合
```
$ unset PATH
```

## 参考URL
- [Pathを通すとは、環境変数とは](https://qiita.com/fuwamaki/items/3d8af42cf7abee760a81)
