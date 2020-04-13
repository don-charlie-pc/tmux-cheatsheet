# tmux-cheatsheet
My tmux cheatsheet

## Sessions

### New Session

* `tmux new [-s name] [cmd]` (`:new`) - new session

### Switch Session

* `tmux ls` (`:ls`) - list sessions
* `tmux switch [-t name]` (`:switch`) - switches to an existing session
* `tmux as [id] [-t name]` (`:attach`) - attaches to an existing session
* `<Ctrl-b>c` (`:detach`) - detach the currently attached session

### Session Management

* `<Ctrl-b>s` - list sessions
* `<Ctrl-b>$` - name session

### Close Session

* `tmux kill-session [-t name]` (`:kill-session`)

## Windows

### New Window

* `<Ctrl-b>c` (`:neww [-n name] [cmd]`) - new window

### Cursor Movement

* `<Ctrl-b>[i]` (`:selectw -t [i]`) - go to window `[i]`
* `<Ctrl-b>l` - go to last window
* `<Ctrl-b>p` - go to previous window
* `<Ctrl-b>n` - go to next window

### Window Management

* `<Ctrl-b>T` - rename window
* `<Ctrl-b>,` - rename window
* `<Ctrl-b>w` - list all windows
* `<Ctrl-b>f` - find window by name
* `<Ctrl-b>.` - move window to another session (promt)
* `:movew` - move window to next unused number

### Close Window

* `<Ctrl-b>&` (`:kill-window`) - kill window

## Panes

### New Pane

* (%) `<Ctrl-b>|` (`:splitw [-v] [-p width] [-t focus] [cmd]`) - split current pane vertically
* (") `<Ctrl-b>s` (`:splitw -h [-p width] [-t focus] [cmd]`) - split current pane horizontally

### Cursor Movement

* (o) `<Ctrl-b><Tab>` (`:selectp -t :.+`) - move cursor to the next pane
* `<Ctrl-b><Up>` (`:selectp -U`) - move cursor to the pane above
* `<Ctrl-b><Down>` (`:selectp -D`) - move cursor to the pane below
* `<Ctrl-b><Left>` (`:selectp -L`) - move cursor to the pane to the left
* `<Ctrl-b><Right>` (`:selectp -R`) - move cursor to the pane to the right
* `:selectp [i]` - move cursor to the pane `[i]`

### Panes Management

* (`:swap-pane -U`) - move current pane up
* (`:swap-pane -D`) - move current pane down
* `<Ctrl-b>{` (`:swap-pane -L`) - move current pane to the left
* `<Ctrl-b>}` (`:swap-pane -R`) - move current pane to the right
* `<Ctrl-b>q` - show pane numbers (type number to move cursor)
* `<Ctrl-b><Space>` - toggle pane arrangements

### Resize Pane

* `:resize-pane -U [i]` - move horizontal divider up by `[i]` lines
* `:resize-pane -D [i]` - move horizontal divider down by `[i]` lines
* `:resize-pane -L [i]` - move vertical divider left by `[i]` columns
* `:resize-pane -R [i]` - move vertical divider right by `[i]` columns

`resize-pane [-DLRUZ] [-x width] [-y height] [-t target-pane] [adjustment]`

### Close Pane

* `<Ctrl-b>x` (`:kill-pane`) - kill current pane

## Misc

* `<Ctrl-b>t` - show time
* `<Ctrl-b>r` - reload config

# tmux cheatsheet

start new with session name:

    tmux new -s myname

attach:

    tmux a  #  (or at, or attach)

attach to named:

    tmux a -t myname

list sessions:

    tmux ls

kill session:

    tmux kill-session -t myname

In tmux, hit the prefix `ctrl+b` and then:

## Sessions

    :new<CR>  new session
    s  list sessions
    $  name session

## Windows (tabs)

    c           new window
    ,           name window
    w           list windows
    f           find window
    &           kill window
    .           move window - prompted for a new number
    :movew<CR>  move window to the next unused number

## Panes (splits)

    %  horizontal split
    "  vertical split
    
    o  swap panes
    q  show pane numbers
    x  kill pane
    ⍽  space - toggle between layouts

## Window/pane surgery

    :joinp -s :2<CR>  move window 2 into a new pane in the current window
    :joinp -t :1<CR>  move the current pane into a new pane in window 1

* [Move window to pane](http://unix.stackexchange.com/questions/14300/tmux-move-window-to-pane)
* [How to reorder windows](http://superuser.com/questions/343572/tmux-how-do-i-reorder-my-windows)

## Misc

    d  detach
    t  big clock
    ?  list shortcuts
    :  prompt
