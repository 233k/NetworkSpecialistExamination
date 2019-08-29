# SQL

## 構造
```
句 句? 値 (句 値){n}
n > 0
```

## 文の種類
- SELECT
- INSERT
- UPDATE
- DELETE
- DROP
- etc...

## SELECT文
### 評価順序
1. FROM
1. ON
1. JOIN
1. WHERE
1. GROUP BY
1. HAVING
1. SELECT
1. DISTINCT
1. ORDER BY
1. TOP（LIMIT）

### GROUP BY と HAVING と集約関数
#### 集約関数
- SUM
- AVG
- COUNT
- max
- min
- etc...

SELECT文にGROUP BY句が含まれる場合、必ずSELECT句の対象に集約関数の値が入る

SELECT文にHAVING句が含まれる場合、必ずHAVING句の対象に集約関数を使った条件式が入る

```
2020年度の平均点数が600点以上となったクラスのクラス名と平均点数の一覧を取得するSQL文

SELECT class, AVG(score) FROM test_result
    WHERE date BETWEEN '2020-04-01' AND '2021-03-31'
    GROUP BY class HAVING AVG(score) >= 600
```


# 参考
- https://qiita.com/suzukito/items/edcd00e680186f2930a8