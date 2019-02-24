# Ubuntuについて記述する

## netplanとはなんぞや
- Ubuntuが作ったネットワーク設定ツール
  - YAMLで記述する
  - 実際にはYAMLで記述した設定をnetworkdなどで反映させるラッパーアプリ
  - こんなん

```
  network:
  version: 2
  renderer: NetworkManager
  ethernets:
    eno1:
      addresses:
      - 192.168.1.200/24
      gateway4: 192.168.1.1
      dhcp4: false
      nameservers:
        addresses:
        - 192.168.1.1
  version: 2
```

