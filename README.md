# vscode-sync-settings

My VSCode settings, synchronized by https://github.com/shanalikhan/code-settings-sync

## Install vscode extension `Sync Settings`

https://marketplace.visualstudio.com/items?itemName=zokugun.sync-settings

## Setup - push & pull with `type: file` and self-managed git repo

### 1. Git clone `pastleo/vscode-sync-settings`

```sh
mkdir -p ~/.config
git clone https://github.com/pastleo/vscode-sync-settings.git ~/.config/vscode-sync-settings
cd ~/.config/vscode-sync-settings
git remote set-url --push origin git@github.com:pastleo/vscode-sync-settings.git
```

### 2. Run command (by Ctrl+Shift+P): `> Sync Settings: Open the repository settings`

```yml
hostname: ""
profile: main
repository:
  type: file
  path: ~/.config/vscode-sync-settings
```

## Setup - pull only with remote `type: git`

### 1. Run command (by Ctrl+Shift+P): `> Sync Settings: Open the repository settings`

```yml
hostname: ""
profile: main
repository:
  type: git
  url: https://github.com/pastleo/vscode-sync-settings.git
  branch: main
```

---

## Download setting

### 1. Git pull if with `type: file` and self-managed git repo

```sh
cd ~/.config/vscode-sync-settings
git pull
```

### 2. `> Sync Settings: Download (repository -> user)`

VsCode might restart, if it failed to start after closing, just start manually

> don't know why, nvim integration extension is disabled, need to enable manually after first `Download`

---

## Upload setting

### 1. Close all files and projects/folders

`File` > `Close Folder`

### 2. `> Sync Settings: Upload (user -> repository)`

to copy settings to git repository and git commit

### 3. Review changes, git commit & push

```sh
cd ~/.config/vscode-sync-settings
git diff
git add --all
git commit -m "update -- $(date +"%Y-%m-%dT%H:%M:%S%z")"
git push
```