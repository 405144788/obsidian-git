# Obsidian Git 中文汉化版 🇨🇳

[![GitHub release](https://img.shields.io/github/v/release/405144788/obsidian-git?style=for-the-badge&sort=semver)](https://github.com/405144788/obsidian-git/releases/latest)
[![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)](LICENSE)

> 基于 [Vinzent03/obsidian-git](https://github.com/Vinzent03/obsidian-git) v2.38.2，增加 **简体中文 (zh-CN)** 界面翻译。

## 简介

Obsidian Git 插件的社区汉化分支。在 Obsidian 内集成 Git 版本控制——自动 commit、pull、push，查看变更记录，全部中文界面。

## 与上游的区别

- ✅ 完整的 i18n 框架（`src/lang/`）
- ✅ 设置页面、命令面板、Source Control、History View 全部汉化
- ✅ 自动跟随 Obsidian 语言设置，也可手动选 `zh-cn`
- ✅ 通过 GitHub Actions 自动构建

## 安装

### BRAT 安装
1. 安装 [BRAT](https://github.com/TfTHacker/obsidian42-brat) 插件
2. BRAT 中添加 `405144788/obsidian-git`

### 手动安装
1. 从 [Releases](https://github.com/405144788/obsidian-git/releases) 下载最新版
2. 将 `main.js`、`manifest.json`、`styles.css` 放入 `.obsidian/plugins/obsidian-git/`
3. 重启 Obsidian

## 开发

```bash
git clone https://github.com/405144788/obsidian-git.git
cd obsidian-git
pnpm install
pnpm run build
```

## 致谢

- 原始插件：[Vinzent03/obsidian-git](https://github.com/Vinzent03/obsidian-git)（MIT）
- 中文 i18n 贡献：[CY1211NET](https://github.com/CY1211NET)（PR #1063）
- 初始作者：[denolehov](https://github.com/denolehov)

---

# English

All setup instructions (including mobile), common issues, tips, and advanced configuration can be found in the 📖 [full documentation](https://publish.obsidian.md/git-doc).

> Mobile users: The plugin is **highly unstable ⚠️ !** Please check the dedicated [Mobile](#-mobile-support-%EF%B8%8F--experimental) section below.

## Key Features

- 🔁 **Automatic commit-and-sync** (commit, pull, and push) on a schedule.
- 📥 **Auto-pull on Obsidian startup**
- 📂 **Submodule support** for managing multiple repositories (desktop only and opt-in)
- 🔧 **Source Control View** to stage/unstage, commit and diff files - Open it with the `Open source control view` command.
- 📜 **History View** for browsing commit logs and changed files - Open it with the `Open history view` command.
- 🔍 **Diff View** for viewing changes in a file - Open it with the `Open diff view` command.
- 📝 **Signs in the editor** to indicate added, modified, and deleted lines/hunks (desktop only).
- GitHub integration to open files and history in your browser

> For detailed file history, consider pairing this plugin with the [Version History Diff](obsidian://show-plugin?id=obsidian-version-history-diff) plugin.

## UI Previews

### 🔧 Source Control View

Manage your file changes directly inside Obsidian like stage/unstage individual files and commit them.

![Source Control View](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/source-view.png)

### 📜 History View

Show the commit history of your repository. The commit message, author, date, and changed files can be shown. Author and date are disabled by default as shown in the screenshot, but can be enabled in the settings.

![History View](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/history-view.png)

### 🔍 Diff View 

Compare versions with a clear and concise diff viewer.
Open it from the source control view or via the `Open diff view` command.

![Diff View](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/diff-view.png)

### 📝 Signs in the Editor

View line-by-line changes directly in the editor with added, modified, and deleted line/hunk indicators. You can stage and reset changes right from the signs. There also commands to navigate between hunks and stage/reset hunks under the cursor. Needs to be enabled in the plugin settings.

![Signs](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/signs.png)

## Available Commands
> Not exhaustive - these are just some of the most common commands. For a full list, see the Command Palette in Obsidian.

- 🔄 Changes
  - `List changed files`: Lists all changes in a modal
  - `Open diff view`: Open diff view for the current file
  - `Stage current file`
  - `Unstage current file`
  - `Discard all changes`: Discard all changes in the repository
- ✅ Commit
  - `Commit`: If files are staged only commits those, otherwise commits only files that have been staged
  - `Commit with specific message`: Same as above, but with a custom message
  - `Commit all changes`: Commits all changes without pushing
  - `Commit all changes with specific message`: Same as above, but with a custom message
- 🔀 Commit-and-sync
  - `Commit-and-sync`: With default settings, this will commit all changes, pull, and push
  - `Commit-and-sync with specific message`: Same as above, but with a custom message
  - `Commit-and-sync and close`: Same as `Commit-and-sync`, but if running on desktop, will close the Obsidian window. Will not exit Obsidian app on mobile.
- 🌐 Remote
  - `Push`, `Pull`
  - `Edit remotes`: Add new remotes or edit existing remotes
  - `Remove remote`
  - `Clone an existing remote repo`: Opens dialog that will prompt for URL and authentication to clone a remote repo
  - `Open file on GitHub`: Open the file view of the current file on GitHub in a browser window. Note: only works on desktop
  - `Open file history on GitHub`: Open the file history of the current file on GitHub in a browser window. Note: only works on desktop
- 🏠 Manage local repository
  - `Initialize a new repo`
  - `Create new branch`
  - `Delete branch`
  - `CAUTION: Delete repository`
- 🧪 Miscellaneous
  - `Open source control view`: Opens side pane displaying [Source control view](#sidebar-view)
  - `Open history view`: Opens side pane displaying [History view](#history-view)
  - `Edit .gitignore`
  - `Add file to .gitignore`: Add current file to `.gitignore`

## 💻 Desktop Notes

### 🔐 Authentication

Some Git services may require further setup for HTTPS/SSH authentication. Refer to the [Authentication Guide](https://publish.obsidian.md/git-doc/Authentication)

### Obsidian on Linux

- ⚠️  Snap is not supported due to its sandboxing restrictions.
- ⚠️  Flatpak is not recommended, because it doesn't have access to all system files. They are actively fixing many issues, but there are still issues. Especially with more advanced setups.
- ✅ Please use AppImage or a full access installation of your system's package manager instead ([Linux installation guide](https://publish.obsidian.md/git-doc/Installation#Linux))

## 📱 Mobile Support (⚠️  Experimental)

The Git implementation on mobile is **very unstable**! I would not recommend using this plugin on mobile, but try other syncing services.

One such alternative is [GitSync](https://github.com/ViscousPot/GitSync), which is available on both Android and iOS. It is not associated with this plugin, but it may be a better option for mobile users. A tutorial for setting it up can be found [here](https://viscouspotenti.al/posts/gitsync-all-devices-tutorial).

> 🧪 The Git plugin works on mobile thanks to [isomorphic-git](https://isomorphic-git.org/), a JavaScript-based re-implementation of Git - but it comes with serious limitations and issues. It is not possible for an Obsidian plugin to use a native Git installation on Android or iOS.

### ❌ Mobile Feature Limitations

- No **SSH authentication** ([isomorphic-git issue](https://github.com/isomorphic-git/isomorphic-git/issues/231))
- Limited repo size, because of memory restrictions
- No rebase merge strategy
- No submodules support

### ⚠️ Performance Caveats

> [!caution]
> Depending on your device and available free RAM, Obsidian may
>
> - crash on clone/pull
> - create buffer overflow errors
> - run indefinitely.
>
> It's caused by the underlying git implementation on mobile, which is not efficient. I don't know how to fix this. If that's the case for you, I have to admit this plugin won't work for you. So commenting on any issue or creating a new one won't help. I am sorry.

### Tips for Mobile Use:

If you have a large repo/vault I recommend to stage individual files and only commit staged files.

## 🙋 致谢

- 原始插件：[denolehov/obsidian-git](https://github.com/denolehov/obsidian-git) → [Vinzent03/obsidian-git](https://github.com/Vinzent03/obsidian-git)
- 中文 i18n 贡献：[CY1211NET](https://github.com/CY1211NET)（PR #1063）
- Line Authoring：[GollyTicker](https://github.com/GollyTicker)
- 汉化版维护：[405144788](https://github.com/405144788)
