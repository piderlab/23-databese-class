# データベース　演習

## 扱うデータについて

本講義の演習で扱うデータは以下の通りです。

- [history.csv](./history.csv) : 乗車履歴
- [spot.csv]() : 目的地の DB
- [trip.csv]() : 駐車履歴
- [user.csv]() : ユーザー情報

## Installation

このデータをクローンまたはダウンロードして，各自それぞれのデータについて分析を行います。
クローンするためにはレポジトリへのアクセス権限が必要です。

```bash
git clone git@github.com:piderlab/.git
```

## Example Analysis

二つの例を以下に示します。
是非，演習の参考にしてください。

- [sample_1](https://github.com/piderlab/NAISMoNData-23/blob/main/2023_database_ta/sample_code.ipynb) : 乗車人数が 3 人以上の時，どの spot へ行ったか
- [sample_2]() :

## Data Handling

本演習では，csv ファイルを扱います。その為，分析する際にはデータフレームとして扱うのが良いと思われます。
以下に，初歩的なデータの扱い方について示します。

```bash
# csvファイルをデータフレームとして読み込む
import pandas as pd
df = pd.read_csv("相対パス")
```

```bash
# csvファイル内の日付データ列をdatetime型にしてデータフレームとして読み込む
import pandas as pd
df = pd.read_csv("相対パス", parse_dates=["列名"])
```

```bash
# 読み込んだデータフレーム内にあるリストデータ列をlist型に変換する
import json
df["列名"] = df["列名"].map(json.loads)
```

```bash
# テーブル結合(内部結合)
marged_df=pd.merge(結合したいデータフレームの格納された変数名1, 結合したいデータフレームの格納された変数名2, on="結合対象となる列名")
#　不必要な列は即除しておく
df_3 = df_3.loc[:,["必要な列名","必要な列名","必要な列名"]]
# locで指定した順番にDataFrameの各列を並べ替えることができます。
```

## 参考リンク

- テーブル結合 https://note.nkmk.me/en/python-pandas-merge-join/
- データ集計 https://note.nkmk.me/python-pandas-groupby-statistics/
- データの重複削除 https://note.nkmk.me/python-pandas-duplicated-drop-duplicates/
- ソート https://note.nkmk.me/python-pandas-sort-in-any-order/
- ソート https://note.nkmk.me/python-pandas-sort-values-sort-index/
- グラフ描画 https://plotly.com/python/
