# Webpack

## Webpackとは
モジュールバンドラのこと

## モジュールバンドラとは
複数のモジュールを1つにまとめてファイルとして出力するツールのこと

## 便利な使い方
### importするファイルパスの定義の時のエイリアスの設定のやり方
下記のように書ける。

```
resolve: {
    alias: {
        '@': resolve(__dirname, 'src'),
    },
},
```


## 参考文献
- [webpack 4 入門](https://qiita.com/soarflat/items/28bf799f7e0335b68186)
- [Webpack を使っていてファイルの相対パスを書くのがつらくなったとき](https://kitak.hatenablog.jp/entry/2017/09/04/192010)
