# Pythonについての諸々

## with構文
- [調べようと思ったら既にまとめられていた](https://reiki4040.hatenablog.com/entry/20130331/1364723288)
    - 要するに開始時と終了時のフックを呼び出す様になっているクラス

## py3の仮想環境の作り方

```
$ mkdir py3
$ python3 -m venv py3
$ source py3/bin/activate
```

## pipで必要なパッケージを自動インストール

```
$ cd <motono directory>
$ pip freeze > requirements.txt
$ cd <other directory>
$ pip install -r requirements.txt
```
