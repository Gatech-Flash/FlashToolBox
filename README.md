# FlashToolBox
Tool Box for Flash Members

## Python Toolkits
[Github](https://github.com/Gatech-Flash/FlashPythonToolbox)

```
pip install flashtool
```

### File logger
For every print function, we print a copy to file without changing the whole file.  Similar to `tee`

Example: 
```python
from flashtool import Logger
import sys
sys.stdout = Logger("path/to/log/file/log.txt")
```
### Email Module
```python
# Example
from flashtool import send_email
send_email(receiver_email="xxx@gmail.com", subject="Hi", message="first email")
```
### Job Tracker
Send a email when job (pid) is done.
```python
# Example
from flashtool import trackpid
trackpid(12345,5,"xxx@gmail.com")
trackpid([1357,2468],5,"xxx@gmail.com")
```

## Server Toolkits
[Download](https://hmjianggatech.github.io/files/atom_vim_zsh_tmux_configs.zip)

It contains setup configs for `tmux`, `zsh`, `vim`, `anaconda`.

**Usage**
```
mkdir toolkits
cd toolkits
wget https://hmjianggatech.github.io/files/atom_vim_zsh_tmux_configs.zip
unzip atom_vim_zsh_tmux_configs.zip
sh depoly_on_server.sh
```

### Vim

cheat sheet: https://vim.rtorr.com/

- `i`: insert
- `v`: visual
- `V`: visual, line mode
- `esc`: quit mode
- `:q`: quit
- `:wq`: save+quit
- `:w`: save
- `space + enter`: search (`n` for next, `N` for previous)
- `y`: copy
- `p`: paste
- `d`: cut
- `dd`: cut line
- `shift + up/down`: move the line
- `shift + ,/.`: tab, indent 
- `u`: undo
- `Ctrl + r`: redo
- `, + nn`: open/close NERD-tree

In NERD-tree:
- `?`: show help
- `shift + i`: show hidden files.
- `t`: open in new tab
- `enter`: open in current tab


### Tmux

[CheatSheet](https://tmuxcheatsheet.com/)

- `tmux`: open new session
- `tmux a`: attach the last session

In tmux (Session > Windows(Tabs) > Panes)
- `Ctrl+b` `d`: detach
- `Ctrl+b` `m`: turn on/off mouse mode
- `Ctrl+b` `s`: switch session
- `Ctrl+b` `$`: rename session
- `Ctrl+b` `:new -s xxx`: new session with name 'xxx'
- `Ctrl+b` `c`: new window 
- `Ctrl+b` `&`: close window (all panes)
- `Ctrl+b` `"`: Split pane horizontally
- `Ctrl+b` `%`: Split pane vertically
- `Ctrl+b` `x`: close pane 


### Zsh

### PDB & IPDB

```
# set up break points
import ipdb; ipdb.set_trace()
```

PDB Cheat Sheet: [link](https://appletree.or.kr/quick_reference_cards/Python/Python%20Debugger%20Cheatsheet.pdf)

`q`: quit

### GPU usage
```
CUDA_VISIBLE_DEVICES=3 python run.py
```
`nvidia-smi`

## Docker
[link](https://github.com/Gatech-Flash/FlashToolBox/blob/master/Docker.md)

## Linux commends
- `htop`
- `ls`
- `cd`
- `touch`

**file processing**
- ` > `
- `cat`
- `head`  `head -n 5`
- `tail`  `tail -n 5`
- `|tee`
- `grep`


## Someting Else
[deepmind interview killer](https://hmjianggatech.github.io/files/questionlist.xlsx)


