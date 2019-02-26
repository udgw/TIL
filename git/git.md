# Git
## push
- cmd_pushという下請け関数が受け持っている

- 実態はbulitin/push.cに実装されている

## 資料
- [refspecについて](https://www.slideshare.net/ikdysfm/5gitrefspec)


- gitは差分管理ではない
    - しかし今は、.packファイルなどを使用して差分管理している
        - それ以外のコミットがないものは普通の旧来のオブジェクトファイルを使用している

