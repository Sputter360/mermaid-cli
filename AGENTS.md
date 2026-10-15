# AI作業ルール — mermaid-cli

1. README.md、PROJECT_STATUS.md、docs/HANDOFF_AUDIT.mdと対象の仕様・テストを読む。監査日以後のbranch/PR更新を確認する。
2. 編集前にgit status、branch、worktree、stashを確認し、ユーザーの未コミット成果を保全する。main/masterから目的別branchを作り、既存branchの強制再作成・force-pushをしない。
3. 既存資産を削除せず、秘密・認証情報・実患者/個人情報を追加しない。実データが必要な試験は合成入力で代替するか未実施を記録する。
4. CONTRIBUTING.md、building.md、package.json、.github/workflows/test.ymlを参照する。通常の公開依存復元に認証tokenを新規追加しない。fork内の成果と上流に採用済みの機能を区別する。
5. 対象commit・環境・コマンド・exit code・件数を記録し、PASS/FAIL/NOT RUN/BLOCKEDを分ける。テストの削除・緩和で成功にしない。文書だけの変更はリンク・差分を検証し、全機能を再検証したと主張しない。
6. 終了時にPROJECT_STATUS.mdとdocs/HANDOFF_TEMPLATE.mdを使い、変更・未統合成果・未確認事項・次の具体的な一手を残す。
