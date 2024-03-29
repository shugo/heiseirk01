# TextbringerでつくるTextbringer

平成Ruby会議01  2019-12-14




前田 修吾

株式会社ネットワーク応用通信研究所

## この発表を聴いた人が何を持ち帰れるか

* Rubyの動的な性質を活かす方法とTextbringerステッカー

## Textbringerステッカー

![Textbringerステッカー](sticker.jpg)

## Textbringer

* テキストエディタ
* Rubyで書いたEmacs
* 端末で動く
* メールの読み書きもできる
* 今このプレゼンテーションでも使っている

## 名前の由来

* Stormbringer
    * 黒の剣
    * マイクルムアコックのエルリックサーガに登場
    * 殺した相手の魂を啜ってエルリックに力を与える
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

![エディタ戦争](editor_war.jpg)

## Cosmic Balanceの危機

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

* バッファやウィンドウなどがオブジェクト
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

## evalは危険

* 混沌の力
* 強力なので何でもできる
    * 多くの場合強力すぎる
    * Webアプリケーションで使うと怒られがち
* そこを上手く使うのが腕の見せどころ

## 混沌の力

* 動的型（静的型なし）
    * プログラムに誤りがあっても途中までは実行できる
* オブジェクト指向プログラミング
    * 状態変化を直感的に記述できる

## 法の力

* 静的型
    * 実行しなくてもプログラムの誤りを検出できる
* 関数プログラミング
    * 入力が同じなら必ず同じ出力が得られる

## どちらを選ぶか

* どちらにも魅力がある
* 作るものがはっきりしないまま、ちょっとずつプログラムを変えていく楽しさ
* コンパイル通ってから実行したら一発で動いた！という気持ちよさ

## デモ

* indent_new_comment_line コマンドを作成してM-jに割り当てる

## まとめ

* evalを使おう
