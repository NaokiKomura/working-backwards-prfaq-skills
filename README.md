# Working Backwards PR/FAQ Skills

Amazon の **Working Backwards**（顧客から逆算する）の考え方に沿って、人と AI が協力して **PR/FAQ**（未来のプレスリリース＋よくある質問）を作り、レビューし、作るかどうかを判断するための Claude Skills です。

## 工程と分担

| 段階 | 内容 | 人 | AI | スキル |
|---|---|---|---|---|
| 0 受付 | アイデア・制約・意思決定者の確認 | 背景とデータを渡す | 不足情報を質問、成果物の器を作る | `working-backwards-prfaq` |
| 1 顧客と課題 | 5つの問い（顧客は誰か／課題は何か／最重要の便益は何か／なぜわかるのか／体験はどうなるか） | 顧客と課題を1つに絞り承認 | 1問ずつ質問、仮説台帳の初版 | 同上 |
| 2 PR | 1ページ未満の未来の発表文 | 便益と方向性を選ぶ | 2案作成、長さ・用語・明快さの自己点検 | 同上 |
| 3 FAQ | 外部FAQ・内部FAQ | 数字・制約・社内事情を記入 | 質問を出し切り「答えられる／人の情報が必要／未知」に分類 | 同上 |
| 4 レビュー | 黙読 → 質疑 → 書き直し の反復 | 本番会議を開き、指摘の採否を決める | 5つの立場で事前レビュー、会議準備、書き直し案、改訂ログ | `prfaq-review-meeting` |
| 5 検証と判断 | 仮説検証 → Go／再提出／見送り → 開発への引き継ぎ → 発売後の振り返り | 検証を実施し最終判断 | 検証計画、判断資料、要件の骨子、振り返り表 | `prfaq-decision-handoff` |

## 共通ルール

- **AI は顧客の声・数字・市場規模を作らない。** 根拠のない記述には `［仮説］`、人が確かめる値には `［要確認］` を付け、想定の顧客コメントは「（想定）」と明記する。
- **段階ごとにゲートを置き、人の承認を得てから進む。**
- 3つのスキルは同じ成果物（PR/FAQ本体・仮説台帳・改訂ログ）を引き継ぐ。

## 使い方

`skills/` 配下の各フォルダを、Claude のスキルとしてアップロード（または `~/.claude/skills/` に配置）してください。

- 「新しいサービスのPR/FAQを作りたい」→ `working-backwards-prfaq`
- 「このPR/FAQをレビューして」→ `prfaq-review-meeting`
- 「仮説を検証してGo/No-Goを判断したい」→ `prfaq-decision-handoff`

## 参考

- Colin Bryar, Bill Carr『Working Backwards』（2021）
- Werner Vogels, "AWS Lambda turns 10: A rare look at the doc that started it"（2024）

Amazon、AWS、Working Backwards は各社の名称です。本リポジトリは Amazon と無関係の非公式なものです。
