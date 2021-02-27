# Markov Algorithm Offline

- 基本仕様: Markov Algorithm Online https://mao.snuke.org/
- 一般的な処理を可能にするために以下の仕様を追加
  - ステップ数制限を廃止
  - 文字列長制限を廃止
  - コード長制限を廃止
  - コードにエスケープシーケンスを導入
    - `\n` : 改行文字(0x0a) として扱われる
    - `\:` : ':'(0x3a) として扱われる
    - `\\` : '\'(0x5c) として扱われる
    - `\n` でも `\:` でも　`\\` でもない単発 `\` の扱いは、エラーもしくは処理系依存の動作として扱う

## 使用例

``` console
$ cat append-t.mao
tb:bt
t::t
:t

$ echo bbbbb | python markov_algorithm.py append-t.mao
bbbbbt
```

# サンプル
- samples/append-t.mao
  - 上記例と同様
- samples/cat.mao
  - `cat` と同様の動作をする
- samples/hello.mao
  - `Hello: World!\n` を標準入力で受け取った文字列の先頭に追加する
