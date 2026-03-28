# claude-config

Claude Code の設定ファイル (`CLAUDE.md`) を管理するリポジトリ。

## 仕組み

**シンボリックリンク**を使って `~/.claude/CLAUDE.md` とリポジトリのファイルを連動させています。

```
~/.claude/CLAUDE.md  →（リンク）→  ~/dev/claude-config/CLAUDE.md  →  GitHub
```

シンボリックリンクとは「別名・ショートカット」のようなもので、どちらのパスで開いても同じファイルを編集することになります。そのため、Claude Code が読む `~/.claude/CLAUDE.md` を編集するだけで、リポジトリ側も自動的に更新されます。

---

## Mac：新しいマシンへの初期セットアップ

```bash
# 1. リポジトリをクローン（~/dev/ に保存）
git clone https://github.com/lyrica7099/claude-config ~/dev/claude-config

# 2. 既存の CLAUDE.md をバックアップ
mv ~/.claude/CLAUDE.md ~/.claude/CLAUDE.md.bak

# 3. シンボリックリンクを作成
ln -s ~/dev/claude-config/CLAUDE.md ~/.claude/CLAUDE.md
```

これで完了。以降は `~/.claude/CLAUDE.md` を普通に編集するだけで OK。

---

## Mac：CLAUDE.md を編集して GitHub に保存する

1. `~/.claude/CLAUDE.md` を任意のエディタで編集（シンボリックリンクなので自動的にリポジトリ側も更新される）
2. ターミナルで以下を実行：

```bash
cd ~/dev/claude-config
git add CLAUDE.md
git commit -m "update CLAUDE.md"
git push
```

---

## Mac：GitHub の最新版を取り込む

```bash
cd ~/dev/claude-config
git pull
```

シンボリックリンク経由で `~/.claude/CLAUDE.md` にも即座に反映されます。

---

## Windows：新しいマシンへの初期セットアップ

**1. リポジトリをクローン**

```powershell
git clone https://github.com/lyrica7099/claude-config $HOME\dev\claude-config
```

**2. シンボリックリンクを作成**（管理者権限のコマンドプロンプトで実行）

```cmd
mklink %USERPROFILE%\.claude\CLAUDE.md %USERPROFILE%\dev\claude-config\CLAUDE.md
```

**3. 最新版を取り込む場合**

```powershell
cd $HOME\dev\claude-config
git pull
```

---

## Mac：ダイレクトダウンロード方式（シンボリックリンクを使わない場合）

同期は手動になるが、シンプルに使いたい場合：

```bash
curl -o ~/.claude/CLAUDE.md https://raw.githubusercontent.com/lyrica7099/claude-config/main/CLAUDE.md
```
