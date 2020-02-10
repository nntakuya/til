# 構造体について

## 構造体とは
プログラミング言語における変数の型の1つ。
特徴として、中身の構造を自分で決められること。


## メリット
- 変数定義するときに、構造体で定義した分のメモリを確保してくれる
- データ型を定義してくれる


```go
func main() {
    // newでuser構造体分の領域を確保して、初期化して、そのポインタを返す
    u1 := new(user)
    // ポインタが返ってきているので下記の書き方でもOK
    // (*u).name = "fujimoto"
    u1.name = "fujimoto"
    u1.score = 200

    fmt.Println(u1)

    // 初期化する時に直接値を与える事も可能
    // こちらの場合はポインタではない構造体のデータが入ってくる。
    u2 := user{name: "arita", score: 300}
    fmt.Println(u2)
}
```


## インターフェイスとの違い
インターフェイスは、必要なメソッドを一覧化したもの。





## 参照
- [他言語プログラマがgolangの基本を押さえる為のまとめ] (https://qiita.com/tfrcm/items/e2a3d7ce7ab8868e37f7#%E6%A7%8B%E9%80%A0%E4%BD%93%E3%81%AE%E5%AE%9A%E7%BE%A9%E3%81%A8%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89)
- [構造体 (structure)とは｜「分かりそう」で「分からない」でも](https://wa3.i-3-i.info/word13243.html)
- [構造体を使ったプログラム](https://qiita.com/nomunomu0504/items/1a72b0150ea0fcf442b0)

