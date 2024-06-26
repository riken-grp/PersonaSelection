# PersonaSelection

PersonaSelectionはJapanese Persona Chatの対話データを用いて作成された、発話文とその発話文に使用されているペルソナ文が紐づけられたコーパスです。
発話文と発話者の各ペルソナ文に対して3名のアノテータが、ペルソナの反映度に応じて0から2の3段階でラベル付けを行ったデータが含まれています。

** データフォーマット
[raw/](https://github.com/riken-grp/PersonaSelection/tree/main/raw)内に、csvファイルとjsonファイルがありますが、収録されているデータは同一です。
各データには、No、話者、発話、ペルソナ、scoreの5つの情報が含まれます。
| キー | 説明 |
| ---- | ---- |
| No | オリジナルの[JPersona Chat](https://github.com/nttcslab/japanese-dialog-transformers/blob/main/README-jp.md)のどの対話から作成されたかを表します|
| 話者 | 2人の話者(A,B)のどちらの発話かを表します。 |
| 発話 | 話者の発話文を表します | 
| ペルソナ | JPersona Chat内で定義されている話者のペルソナ文5文+発話中に出現した話者の定義されていないペルソナ数文を表します。文が5文以上ある場合は、最初の5文がJPersona Chatに定義されているペルソナで、6文目以降が対話中に出てくるがJPersona Chatには定義されていないペルソナを表します。|
| score | 各ペルソナに対して3名のアノテータが`2`「ペルソナが反映されている」,`1`「ペルソナがやや反映されている」、`0`「ペルソナが反映されている」としてラベル付けを行った結果がjson形式で格納されています。 |


# Bib TeX
本データを使用した結果を公開する場合には、以下の論文を引用ください。
```
@inproceedings{kaiyo2024select,
    title="ペルソナ対話システムにおけるペルソナ選択と応答生成",
    author="吉田快 and 吉野幸一郎 and 品川政太朗 and 須藤克仁 and 中村哲",
    booktitle = "言語処理学会第30回年次大会発表論文集",
    year = "2024",
    pages = "1447--1452"
}
```