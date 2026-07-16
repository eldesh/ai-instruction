# AI Instructions

このリポジトリの `INSTRUCTIONS.md` は、特定のコードやプロジェクトに依存しない一般的なAI向け指示です。

## Codex

Codexのグローバルな指示として使用するには、次のようにシンボリックリンクを作成します。

```sh
ln -s /path/to/repo/ai-instruction.git/INSTRUCTIONS.md ~/.codex/AGENTS.md
```

### Windows版ChatGPTアプリ

Windows版ChatGPTアプリのCodexでは、「設定 > パーソナライズ > カスタム指示」の個人用指示として次のファイルが使用されます。

```text
%USERPROFILE%\.codex\AGENTS.md
```

`INSTRUCTIONS.md` をそのまま使用するには、コマンドプロンプトで次を実行します。

```bat
mkdir "%USERPROFILE%\.codex"
mklink "%USERPROFILE%\.codex\AGENTS.md" "C:\path\to\ai-instruction.git\INSTRUCTIONS.md"
```

`C:\path\to\ai-instruction.git` はこのリポジトリの実際のパスに置き換えます。シンボリックリンクの作成には、Windowsの開発者モードまたは管理者権限が必要です。

Codexが個人用の `AGENTS.md` を読み込む方法については、[Custom instructions with AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md#how-codex-discovers-guidance) を参照してください。

## Claude Code

Claude Codeのユーザー共通の指示として使用するには、次のようにシンボリックリンクを作成します。

```sh
ln -s /path/to/repo/ai-instruction.git/INSTRUCTIONS.md ~/.claude/CLAUDE.md
```
