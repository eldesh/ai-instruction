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

リポジトリがWindows上にある場合、コマンドプロンプトで次を実行します。

```bat
mkdir "%USERPROFILE%\.codex"
mklink "%USERPROFILE%\.codex\AGENTS.md" "C:\path\to\ai-instruction.git\INSTRUCTIONS.md"
```

`C:\path\to\ai-instruction.git` はこのリポジトリの実際のパスに置き換えます。シンボリックリンクの作成には、Windowsの開発者モードまたは管理者権限が必要です。

リポジトリがWSL上にある場合は次のようにします。

```bat
mkdir "%USERPROFILE%\.codex"
mklink "%USERPROFILE%\.codex\AGENTS.md" "\\wsl.localhost\Ubuntu-22.04\path\to\repo\ai-instruction.git\INSTRUCTIONS.md"
```

Codexが個人用の `AGENTS.md` を読み込む方法については、[Custom instructions with AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md#how-codex-discovers-guidance) を参照してください。

## Claude Code

Claude Codeのユーザー共通の指示として使用するには、次のようにシンボリックリンクを作成します。

```sh
ln -s /path/to/repo/ai-instruction.git/INSTRUCTIONS.md ~/.claude/CLAUDE.md
```

### Windows版Claude Code

Windows版Claude Codeでは、ユーザー共通の指示として次のファイルが使用されます。

```text
%USERPROFILE%\.claude\CLAUDE.md
```

Claude Codeではシンボリックリンクの代わりにインポート機能が使えます。

リポジトリがWindows上にある場合、コマンドプロンプトで次を実行します。

```bat
mkdir "%USERPROFILE%\.claude"
echo @C:\path\to\ai-instruction.git\INSTRUCTIONS.md > "%USERPROFILE%\.claude\CLAUDE.md"
```

`C:\path\to\ai-instruction.git` はこのリポジトリの実際のパスに置き換えます。

リポジトリがWSL上にある場合は次のようにします。

```bat
mkdir "%USERPROFILE%\.claude"
echo @\\wsl.localhost\Ubuntu-22.04\path\to\repo\ai-instruction.git\INSTRUCTIONS.md > "%USERPROFILE%\.claude\CLAUDE.md"
```

## 任意の指示

`optional/` には、プロジェクトごとに導入を選択する任意の指示があります。これらのファイルは自動的に読み込まれません。

### 変更対象に基づく `AGENTS.md` の探索

[`optional/target-scoped-agents.md`](optional/target-scoped-agents.md) は、変更対象ファイルごとにプロジェクトルートからその親ディレクトリまでの `AGENTS.md` を確認し、対象に近い指示を優先させるための指示です。

この動作が必要なプロジェクトでのみ、同ファイルの内容をそのプロジェクトのルート `AGENTS.md` にコピーまたは統合してください。グローバルな `INSTRUCTIONS.md` には統合しません。
