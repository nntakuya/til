# ディスプレイ
主にデバッグする際に使用する。

## やり方
1. `fmt`モジュールをインポートする
2. 構造体に名前をつけて定義する
3. 



```rust

use std::fmt;

struct Structure(i32);

impl fmt::Display for Structure {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
      write!(f, "{}", self.0)
  }
}

```
