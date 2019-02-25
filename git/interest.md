# gitに関する雑然とした情報を並べていく
- [gitgeist - backend, 通信規約にgitを使用したSNSの試み](https://github.com/opersys/gitgeist-poc)

# コミットせずに2回Add, Removeしたらどうなるの？
- 予想
    - オブジェクトは作られる
    - コミット履歴には残らない
        - そのとおりだった

- Pro Gitにあった
    - .git/refs/以下のトップのハッシュから参照していくので送信されない
