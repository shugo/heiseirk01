# TextbringerでつくるTextbringer

平成Ruby会議01  2019-12-14




前田 修吾

株式会社ネットワーク応用通信研究所

## この発表を聴いた人が何を持ち帰れるか

* Rubyの動的な性質を活かす方法とTextbringerステッカー

## Textbringerステッカー

![Textbringerステッカー](sticker.jpg)

## アンケート

主に使っているエディタは？

1. Emacs系 (JED/xyzzyなども含む)
2. vi系 (Vim/Neovimなども含む)
3. それ以外

## Textbringer

* テキストエディタ
* Rubyで書いたEmacs
* 端末で動く
* メールの読み書きもできる
* 今このプレゼンテーションでも使っている

## 名前の由来

![Stormbringer](stormbringer.jpg)

## エルリックサーガ

* マイクルムアコックが書いた小説群
* エルリック
    * メルニボネの皇帝
    * 病弱
    * 混沌の神アリオッチに仕える
* Stormbringer
    * 黒の剣
    * 魂を啜ってエルリックにその力を与える
    * 世界を滅ぼすほどの力をもつ
* Textbringerがもたらすのは嵐ではなくテキストなので安全

## 法と混沌、そして天秤

* 法 (Law)
    * 秩序・規律 → 停滞
* 混沌 (Chaos)
    * 多様性・変化 → 破壊
* 宇宙の天秤 (Cosmic Balance)
    * 法と混沌の釣り合い

## Cosmic Balance

![Cosmic Balance](balance.png)

## 法の力が強まりすぎでは？

* 今日は混沌の力の魅力について話します

## ブートストラップ問題

* テキストエディタを書くにはテキストエディタが必要
    1. VimでTextbringerを書く
    2. だいたい動くようになる
    3. TextbringerでTextbringerを書く
    4. Textbringerが壊れる
    5. 1に戻る

## 何もしてないのに壊れた

![何もしてないのに壊れた](textbringer_broken.png)

## Feature #13083

* Regexp#match(nil) and Regexp#match?(nil) now raise TypeError
* 現在はrevert

## TextbringerはRuby実行環境

* バッファやウィンドウがオブジェクト
* 再起動せずに振る舞いを変えられる

## eval_expression

* `M-:`または`M-x eval_expression`で実行
* エコーエリア（最下行）に入力されたRubyプログラムを評価
* 評価結果をエコーエリアに出力

## eval_buffer

* `M-x eval_buffer`で実行
* 現在のバッファの内容をRubyプログラムとして評価
* 評価結果をエコーエリアに出力

## eval_region

* `M-x eval_buffer`で実行
* 現在のバッファの内容をRubyプログラムとして評価
* 評価結果をエコーエリアに出力

## REPL

* Read-Eval-Print Loop
* irbやpry
* ruby -eによるワンライナーとの違い
    * 環境を引きずる

## eval

> ささだ: ここからしばらく、このインタビューの全員に聞いていく質問になります。
> 好きなメソッド、嫌いなメソッドはなんですか？
> まつもと: eval、っていうことなんだけど。
> ささだ: 好きも嫌いも両方、でしたね。今でもそうですか？
> まつもと: それは変わらない。eval も、環境を引きずらなければ、何も考えずに
> コンパイルして実行するだけだから、それでいんだけど。

 [Rubyist Hotlinks 【第 1 回】 まつもとゆきひろさん](https://magazine.rubyist.net/articles/0001/0001-Hotlinks.html)

## 環境を引きずる

* 生きているオブジェクトの状態を変えられる
* 生きているオブジェクトの振る舞いも変えられる

## evalは危険

* 強力なので何でもできる
    * 多くの場合強力すぎる
    * Webアプリケーションで使うと怒られがち
* そこを上手く使うのが腕の見せどころ

## 法の力

* 静的型
    * 実行しなくてもプログラムの誤りを検出できる
* 関数プログラミング
    * 入力が同じなら必ず同じ出力が得られる

## 混沌の力

* 動的型（静的型なし）
    * プログラムに誤りがあっても途中までは実行できる
* オブジェクト指向プログラミング
    * 状態変化を直感的に記述できる

## どちらを選ぶか

* どちらにも魅力がある
* コンパイル通ってから実行したら一発で動いた！という気持ちよさ
* 作るものがはっきりしないまま、ちょっとずつプログラムを変えていく楽しさ

## デモ

* indent_new_comment_lineコマンドを作成してM-jに割り当てる

## END
