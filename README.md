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

### WSL上のリポジトリをWindows側のClaude Codeと共有する

Claude CodeをWindowsネイティブ(WSLではなく)で使っている場合、ユーザー共通の指示は次の場所に置きます。

```text
%USERPROFILE%\.claude\CLAUDE.md
```

このリポジトリがWSL側にある場合、シンボリックリンクの作成にはWindowsの開発者モードまたは管理者権限が必要になるため、代わりにCLAUDE.mdの`@`インポート構文を使うと権限なしで参照できます。`%USERPROFILE%\.claude\CLAUDE.md` の中身を次の1行だけにします。

```text
@\\wsl.localhost\<ディストリ名>\path\to\repo\ai-instruction.git\INSTRUCTIONS.md
```

`<ディストリ名>` は `wsl -l` で確認できるディストリビューション名(例: `Ubuntu-22.04`)、パスの残りはこのリポジトリのWSL側の実際のパスに置き換えます。

## 任意の指示

`optional/` には、プロジェクトごとに導入を選択する任意の指示があります。これらのファイルは自動的に読み込まれません。

### 変更対象に基づく `AGENTS.md` の探索

[`optional/target-scoped-agents.md`](optional/target-scoped-agents.md) は、変更対象ファイルごとにプロジェクトルートからその親ディレクトリまでの `AGENTS.md` を確認し、対象に近い指示を優先させるための指示です。

この動作が必要なプロジェクトでのみ、同ファイルの内容をそのプロジェクトのルート `AGENTS.md` にコピーまたは統合してください。グローバルな `INSTRUCTIONS.md` には統合しません。
