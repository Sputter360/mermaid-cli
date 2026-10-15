# AI引き継ぎ監査 — mermaid-cli

監査日: 2026-10-15 UTC。対象: このリポジトリの既定ブランチと監査時に取得できた全branch/PR。
基準: `master` / `e75d048a2374d5823e037c29789dacd621be4a7f`。整備ブランチ: `codex/handoff-audit-20261015`。
この文書は固定時点の観測。再開時は最新のremote refs/PRと照合する。

## 状態と引き継ぎ阻害要因

mermaid-js/mermaid-cliのfork。既定ブランチはmaster。上流向けREADMEと、このfork固有の保守状況を区別する。

監査前のルート資料の欠落: PROJECT_STATUS.md, AGENTS.md。
READMEからの状況・ルール・再開記録への導線を追加し、現在の結果と未確認を区別する。

## ブランチと未統合成果（整備前）

|branch|監査時head|既定branchとの差|
|---|---|---|
|`bugfix/setting-width-to-pngs-from-svgs`|`5aeddbddc3e8d07704e8c64ebc83109a5aab543e`|ahead 1 / behind 349|
|`feature/ERR_REQUIRE_ESM`|`97fa279ebee2322a77fdb7891c0de97538ba2506`|ahead 3 / behind 505|
|`feature/report-syntax-errors-back`|`4e2e1651189ad80db1bdcfde36032efa235fcd53`|ahead 4 / behind 399|
|`feature/update-release-procedure`|`b5d1d708b01f86294a0d55f9fd1ca4613a06b451`|ahead 1 / behind 29|
|`features/issue55-style-for-svg`|`4a7b01647453c60f5fb5a3cc40bae94e0be1657e`|ahead 6 / behind 508|
|`master`|`e75d048a2374d5823e037c29789dacd621be4a7f`|基準|

監査時、このリポジトリのPRは0件。branchの存在だけで採用済みと判断しない。



## テストと証拠の範囲

Jest・standard lint・Puppeteer系の試験資産とtest.ymlが存在する。監査時、このforkのActions実行履歴は0件。今回npm ci / npm test / npm run lint / prepareおよびブラウザ試験はNOT RUN。

## 優先順位付き改善計画

- P1: 5つの分岐はmasterに対し29〜508コミット遅れ、各1〜6独自コミットがある。上流での解決状況と差分の採否を個別に調べる。削除や一括統合をしない。
- P1: building.mdの旧token設定・存在しないtest/state1.mmdを現行のCI/ファイル配置に合う案内へ修正する。
- P2: Node/Chromium環境を固定しnpm ci、npm test、npm run lintを実測する。CIのNode 18.19とサポート方針の更新は依存変更として別レビューする。

P0=開始点や採否を誤る重大な引き継ぎリスク、P1=次作業の前に整備、P2=再現性・継続保守の改善。

## 作業ツリーと保全

監査用の新規cloneは変更前clean、stashなし。元の開発端末・未公開worktree・ローカルのみのcommit/ファイルは確認できない。新規cloneのcleanを元端末のcleanと扱わない。
元端末では `git status --short --branch`、`git branch -avv`、`git worktree list`、`git stash list` を確認し、存在する成果を保全してから継続する。認証付きremote URLや機微な差分は出力・共有しない。
今回、既存branch/PRの統合・削除・履歴改変は行わない。main/masterへ直接書き込まない。

## 次の引き継ぎ

[記録テンプレート](HANDOFF_TEMPLATE.md)に実際のcommit・検証結果・未実施事項・次の作業を記載し、PROJECT_STATUS.mdを更新する。過去のPASSを今回の結果へ昇格しない。

## 今回の実行記録（補足）

環境: Linux / Python 3.12.14 / v24.19.0。対象source SHAは上記の基準。

今回は文書・branch/PR・試験入口の監査を実施。上記でNOT RUNとした機能検証は実行していない。
