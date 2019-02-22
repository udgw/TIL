# Quarser-Frameworkについて記述

Vueを使用したFrameWork, 業務で使用

## FireFox上でのレイアウト崩れ

- q-inputでstyleで幅を指定しつつ入力を右寄せにするとレイアウトが盛大に崩れる
    - leftだと問題ない
    - center不明
    - 対処法がよくわからないので幅指定はしないことに

- q-step内部でdatatableを使用するとDataTableのoverflow文にscrollが出ない
    - すなわち操作できない状態になる
    - q-stepに以下のようにstyle指定すると回避できる。原因不明
        ```
        style="width: 100%; overflow-x: scroll;"
        ```
    - 上記の様にすると、FireFoxではdatatableのみにScrollバーが付くが、Chromeではq-stepの範囲の一番下にScrollが付く(datatableには何もしなくてももともと付いている）

## q-selectの挙動

- q-selectの設定値としてv-model="0"などと設定。この後、値に"0"を渡すと不定状態になる。
    - 何故か暗黙のうちに数字はintに変換される？
    - 混乱を避けるために文字列にすればよいのか？

## キャッチアップ
- v 1.0.0betaが出たらしい
