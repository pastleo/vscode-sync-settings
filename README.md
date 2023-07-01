# vscode-sync-settings

My VSCode settings, synchronized by https://github.com/shanalikhan/code-settings-sync

## Setup

### 1. Git clone `pastleo/vscode-sync-settings`

```sh
mkdir -p ~/.config
git clone https://github.com/pastleo/vscode-sync-settings.git ~/.config/vscode-sync-settings
cd ~/.config/vscode-sync-settings
git remote set-url --push origin git@github.com:pastleo/vscode-sync-settings.git
```

### 2. Install vscode extension `Sync Settings`

https://marketplace.visualstudio.com/items?itemName=zokugun.sync-settings

### 3. Run command (by Ctrl+Shift+P): `> Sync Settings: Open the repository settings`

```sh
# current machine's name, optional; it can be used to filter settings or in the commit message
hostname: ""
# more details at https://github.com/zokugun/vscode-sync-settings/blob/master/docs/hostname.md

profile: main
repository:
  type: git
  path: ~/.config/vscode-sync-settings
  branch: main
```

### 4. `> Sync Settings: Download (repository -> user)`

## Upload setting

### 1. `> Sync Settings: Upload (user -> repository)`

to copy settings to git repository and git commit 

### 2. Git push

```
cd ~/.config/vscode-sync-settings
git push
```