# PROJECT_STATUS

## 引き継ぎ監査の現在地（2026-10-15 UTC）

この整備branchの基準は `master` / `e75d048a2374d5823e037c29789dacd621be4a7f`。mermaid-js/mermaid-cliのfork。既定ブランチはmaster。上流向けREADMEと、このfork固有の保守状況を区別する。

- [監査・未統合branch/PR・優先計画](docs/HANDOFF_AUDIT.md)
- [次回の引き継ぎテンプレート](docs/HANDOFF_TEMPLATE.md)
- 今回の検証と未実施: Jest・standard lint・Puppeteer系の試験資産とtest.ymlが存在する。監査時、このforkのActions実行履歴は0件。今回npm ci / npm test / npm run lint / prepareおよびブラウザ試験はNOT RUN。
- 次の作業: P1: 5つの分岐はmasterに対し29〜508コミット遅れ、各1〜6独自コミットがある。上流での解決状況と差分の採否を個別に調べる。削除や一括統合をしない。

未統合成果の採用・マージは今回未実施。以下に過去記録がある場合、その時点・branchの範囲で読む。
