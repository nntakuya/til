# tmuxプラグインについて


## 困った時
### tmuxの設定について
基本的に、`.tmux.conf`ファイルの変更後の読み込みは、`source`コマンドではなく、
tmux自体の再起動。

下記のリンクも参考になる.
- https://stackoverflow.com/questions/17041647/unable-to-source-tmux-conf



## 設定
### pane

```shell
# Resize pane
bind-key -r H resize-pane -L 5
bind-key -r J resize-pane -D 5
bind-key -r K resize-pane -U 5
bind-key -r L resize-pane -R 5

# Change active pane
bind-key h select-pane -L
bind-key j select-pane -D
bind-key k select-pane -U
bind-key l select-pane -R

```
