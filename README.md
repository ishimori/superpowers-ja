# superpowers-ja

[obra/superpowers](https://github.com/obra/superpowers) のスキル部分を日本語化した Claude Code 用スキルセットです。

**取り込みバージョン:** 5.0.5（2026/3/22 時点）

## 概要

Claude Code に「スキル」という形でワークフローを注入し、AIエージェントの動作を規律正しくガイドするためのプロンプト集です。
スキルは `.claude/skills/` 以下に配置され、Claude Code の `Skill` ツールから呼び出されます。

## 収録スキル一覧

| スキル名 | 用途 |
|---|---|
| `using-superpowers` | 会話開始時に必ず使用。スキルの発見と使用ルールを確立する |
| `brainstorming` | 機能作成・コンポーネント構築など、クリエイティブな作業の前に意図・要件・設計を探索する |
| `writing-plans` | 複数ステップのタスクに対し、コードに触れる前に実装計画を作成する |
| `executing-plans` | 別セッションでレビューチェックポイント付きの実装計画を実行する |
| `subagent-driven-development` | 現在のセッションで独立タスクを含む実装計画をサブエージェントで実行する |
| `dispatching-parallel-agents` | 独立した2つ以上のタスクを並列エージェントに振り分ける |
| `test-driven-development` | 機能・バグ修正の実装コードを書く前にテストから始める |
| `systematic-debugging` | バグ・テスト失敗・予期しない動作に遭遇した際、修正前に根本原因を特定する |
| `verification-before-completion` | 「完了・修正済み」と主張する前に検証コマンドを実行して証拠を確認する |
| `requesting-code-review` | タスク完了・マージ前に作業が要件を満たしているか確認する |
| `receiving-code-review` | コードレビューのフィードバックを受け取る際、盲目的な実装前に技術的に検証する |
| `finishing-a-development-branch` | 実装完了・テスト通過後、マージ・PR・クリーンアップの選択肢を提示する |
| `using-git-worktrees` | 機能開発を現在のワークスペースから隔離するための git worktree を作成する |
| `writing-skills` | 新規スキルの作成・既存スキルの編集・デプロイ前の検証を行う |

## ディレクトリ構成

```
.claude/
└── skills/
    ├── brainstorming/
    │   ├── SKILL.md
    │   └── scripts/          # ブレインストーミング用ビジュアルサーバー
    ├── dispatching-parallel-agents/
    │   └── SKILL.md
    ├── executing-plans/
    │   └── SKILL.md
    ├── finishing-a-development-branch/
    │   └── SKILL.md
    ├── receiving-code-review/
    │   └── SKILL.md
    ├── requesting-code-review/
    │   └── SKILL.md
    ├── subagent-driven-development/
    │   └── SKILL.md
    ├── systematic-debugging/
    │   └── SKILL.md
    ├── test-driven-development/
    │   └── SKILL.md
    ├── using-git-worktrees/
    │   └── SKILL.md
    ├── using-superpowers/
    │   ├── SKILL.md
    │   └── references/       # Codex/Gemini CLI 向けツールマッピング
    ├── verification-before-completion/
    │   └── SKILL.md
    ├── writing-plans/
    │   └── SKILL.md
    └── writing-skills/
        └── SKILL.md
```

## 導入方法

### 新規プロジェクトの場合（推奨）

本リポジトリをそのままスターターキットとして使います。

```bash
git clone https://github.com/ishimori/superpowers-ja your-project
cd your-project
```

`.claude/skills/` がすでに入った状態でプロジェクト開発を始めるだけです。

### 既存プロジェクトへの追加

```bash
cp -r /path/to/superpowers-ja/.claude/skills /your-project/.claude/skills
```

## 使い方

Claude Code との会話中に `Skill` ツール（またはスラッシュコマンド）でスキルを呼び出します。

```
/brainstorming    # 設計フェーズ
/writing-plans    # 計画フェーズ
/test-driven-development  # 実装フェーズ
```

`using-superpowers` スキルは会話開始時に自動的に読み込まれ、他のスキルを適切なタイミングで呼び出すよう Claude を誘導します。

## 元リポジトリ

- 本家: [obra/superpowers](https://github.com/obra/superpowers)
- 取り込みバージョン: 5.0.5（2026/3/22）
