# AI Instructions

このリポジトリの `AGENTS.md` は、特定のコードやプロジェクトに依存しない一般的なAI向け指示です。

## Codex

Codexのグローバルな指示として使用するには、次のようにシンボリックリンクを作成します。

```sh
ln -s /path/to/repo/ai-instruction.git/AGENTS.md ~/.codex/AGENTS.md
```

## Claude Code

Claude Codeは `AGENTS.md` を自動的には読み込まず、ユーザー共通の指示を
`~/.claude/CLAUDE.md` から読み込みます。このリポジトリの `AGENTS.md` を
共通設定として使用するには、次のようにシンボリックリンクを作成します。

```sh
ln -s /path/to/repo/ai-instruction.git/AGENTS.md ~/.claude/CLAUDE.md
```
