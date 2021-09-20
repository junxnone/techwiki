---
Title | tmux plugins
-- | --
Create Date | `2021-09-20T04:36:14Z`
Update Date | `2021-09-20T04:36:14Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/31)

---
# Reference
- [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm)
- [Tmux Resurrect](https://github.com/tmux-plugins/tmux-resurrect)
- [tmux-continuum](https://github.com/tmux-plugins/tmux-continuum)

# Plugins

Plugins | Description
-- | --
tpm | 管理
tmux-sensible |
tmux-resurrect | 保存恢复现场
tmux-continuum | 保存恢复现场


##  tpm

```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

- set `.tmux.conf`

```
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'

run -b '~/.tmux/plugins/tpm/tpm'
```
```
tmux source ~/.tmux.conf
```

> 之后新安装的plugins 会放在 `~/.tmux/plugins/` 下

## Restore plugins

### tmux-resurrect

- Set `.tmux.conf`

```
set -g @plugin 'tmux-plugins/tmux-resurrect'
```

- Install : <kbd>ctrl</kbd> + <kbd>b</kbd> -> <kbd>shift</kbd> + <kbd>i</kbd>
- 保存现场 : <kbd>ctrl</kbd> + <kbd>b</kbd> -> <kbd>ctrl</kbd> + <kbd>s</kbd>
- 恢复现场 : <kbd>ctrl</kbd> + <kbd>b</kbd> -> <kbd>ctrl</kbd> + <kbd>r</kbd>

### tmux-continuum

- Set `.tmux.conf`

```
set -g @plugin 'tmux-plugins/tmux-resurrect'
set -g @plugin 'tmux-plugins/tmux-continuum'
```

> 依赖于 tmux-resurrect

- Install : <kbd>ctrl</kbd> + <kbd>b</kbd> -> <kbd>shift</kbd> + <kbd>i</kbd>
- 选择要恢复的status

```
cd ~/.tmux/resurrect/
rm last
ln -s tmux_xxx.txt last
```

> tmux_xxx.txt 为保存的状态

- 恢复现场 : <kbd>ctrl</kbd> + <kbd>b</kbd> -> <kbd>ctrl</kbd> + <kbd>r</kbd>

