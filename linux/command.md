# コマンド
- rsync -auvz <src> <dist>

    - aオプションはパーミッションなどの情報を保持する
    - uオプションはupdate, 更新があるもののみコピー
    - vオプションは詳細
    - zオプションは圧縮転送

    - distは.ssh/configの方で設定すれば demo:/home/hoge/...のように書ける(下記参照)

```
Host demo
    HostName demo.hogemax.co.jp
    User hogemax 
    Port 22
    IdentityFile ~/udagawa.key
```



