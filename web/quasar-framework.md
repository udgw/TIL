# Vueを使用したFrameWork, Quarser-Frameworkについて記述

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
