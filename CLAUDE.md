# タスク管理システム

Claude Code と GitHub Issues を使った勉強・リサーチのタスク管理システムです。

## 基本ルール

- 返答はすべて日本語
- タスクは必ず GitHub Issue として記録する
- 作業完了後は `Closes #番号` を含む Pull Request を作成する

## タスクのライフサイクル

### 1. タスク受付

ユーザーから指示を受けたら、まず GitHub Issue を作成する。

```
gh issue create --title "タイトル" --body "詳細" --label "priority:high"
```

優先度ラベル：
- `priority:high` - 急ぎ
- `priority:medium` - 通常
- `priority:low` - 余裕があるとき

### 2. ブランチ作成

Issue 番号に対応したブランチを作成して作業する。

```
git checkout -b research/issue-番号-概要
```

### 3. レポート作成

調査・勉強の成果は `reports/` ディレクトリに Markdown で保存する。

ファイル名の形式：`reports/YYYY-MM-DD-テーマ名.md`

レポートの構成：
- ## 概要
- ## 調査内容
- ## わかったこと
- ## 参考資料

### 4. Pull Request 作成

```
gh pr create --title "タイトル" --body "## 概要

内容

Closes #番号"
```

## ディレクトリ構成

```
task-management/
├── CLAUDE.md       # このファイル
└── reports/        # 調査・勉強レポート
```

## ラベル一覧

- `priority:high`
- `priority:medium`
- `priority:low`
- `status:in-progress`
- `status:done`
