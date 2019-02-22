# PGSQLについて
## CASE WHENでなんちゃってポリモーフィズム

- 例えばテーブルAが参照するB,C,Dのテーブルがあるとして、
    - B, C, Dは同種だが微妙に異なるオブジェクトの値を格納している
    - B, C, Dにはそれぞれ共通のc1, c2, c3があるとする
    - B, C, Dはそれぞれ排他であり、Aが参照しているのはこの内の一つだけ
    - 上記条件でAをSELECTするときにB,C,DをJOINしてc1, c2, c3を呼び出したい
- という場合

```
    SELECT
        CASE WHEN B IS NOT NULL THEN B.c1
             WHEN C IS NOT NULL THEN C.c1
             ELSE D.c1
        END AS c1,
        CASE WHEN B IS NOT NULL THEN B.c2
             WHEN C IS NOT NULL THEN C.c2
             ELSE D.c2
        END AS c2,
        CASE WHEN B IS NOT NULL THEN B.c3
             WHEN C IS NOT NULL THEN C.c3
             ELSE D.c3
        END AS c3
    FROM A LEFT JOIN B ON A.b_id = B.id ...
```
のように書くと、 透過的にBCDを判別して値を取れる。
もっとスマートな方法は無いものか？

## 暗黙的なINNER JOIN

```
SELECT
    A.id, B.c1, ...
FROM
    A, B
WHERE
    A.id = B.id_a
```

のようにWHERE句でForeignkeyを指定した場合、INNERJOINが自動的に適応される。

### 出力をファイルにする

```
> \o hoge.txt
> SELECT * FROM hoge_table; -- excute some query
> \o  -- write to hoge.txt
```
