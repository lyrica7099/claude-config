# claude-config

Claude Code の設定ファイル (`CLAUDE.md`) を管理するリポジトリ。

## 新しいデバイスへの適用方法

ターミナルで以下のコマンドを実行してください。

**Mac / Linux**
```bash
curl -o ~/.claude/CLAUDE.md https://raw.githubusercontent.com/lyrica7099/claude-config/main/CLAUDE.md
```

**Windows（PowerShell）**
```powershell
curl -o "$env:USERPROFILE\.claude\CLAUDE.md" https://raw.githubusercontent.com/lyrica7099/claude-config/main/CLAUDE.md
```

## CLAUDE.md を更新した時

Mac で編集後、このリポジトリに反映する：

```bash
cp ~/.claude/CLAUDE.md ~/dev/claude-config/CLAUDE.md
cd ~/dev/claude-config
git add CLAUDE.md
git commit -m "Update CLAUDE.md"
git push
```
