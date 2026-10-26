# skills

コードや設計の理解を固め、日本語の説明を整える Agent Skills。

| スキル | 用途 |
|---|---|
| [comprehend](skills/comprehend/SKILL.md) | コード・変更・設計を調べ、説明と自由回答による確認で理解を固める |
| [japanese-writing](skills/japanese-writing/SKILL.md) | 日本語文書の内容・構成・根拠を整える。他の文章作成・修正スキルによる完全代替・併用が可能 |

## インストール

必要なスキルを選んでインストールする。

```bash
npx skills add xrm07/skills --skill comprehend
npx skills add xrm07/skills --skill japanese-writing
```

`comprehend` は説明指針を同梱しており、単独で導入できる。

## 使用例

```text
$comprehend src/main.rs の設計と成立条件の理解を固めたい
```

```text
$japanese-writing この技術説明の構成と根拠を整えて。
言い回しは、指定した文体修正スキルのルールにも合わせて。
```

### 説明指針を完全に置き換える

```text
$comprehend src/main.rs の理解を固めたい。
説明・文章作成には、導入済みの「指定するスキル名」を使って。
説明・文章作成の指針全体を、そのスキルで置き換えて。
```

代替指定があれば、そのスキルを説明・文章作成の指針として使い、同梱の japanese-writing は読み込まず、内容・構成・根拠の点検も含めて必須にしない。指定がなければ同梱指針を使う。併用を指定すれば従来の役割分担も選べる。comprehend の調査、理解確認、進捗記録は引き続き行う。

他のスキルは別途導入・指定する。特定の製品やスキルには依存しない。

## 配布用ファイルの管理

`skills/japanese-writing/` を公開版の編集元とする。`comprehend` 内の説明指針は単体配布用のコピーであり、公開版を更新したら同期する。ローカル環境のインストール済みスキルとは独立して管理する。
