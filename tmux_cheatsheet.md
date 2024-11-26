
# Tmux Cheat Sheet & Quick Reference

> Master Tmux with these commands and shortcuts! Whether you're managing sessions, windows, or panes, this guide has you covered.

---

## 📂 Sessions

### Starting a Session
- **Start a new session**:  
  ```bash
  $ tmux
  $ tmux new
  $ tmux new-session
  ```
  - `: new`: Start a new session.
- **Start or attach to a session named `mysession`**:  
  ```bash
  $ tmux new-session -A -s mysession
  ```
- **Start a named session**:  
  ```bash
  $ tmux new -s mysession
  ```
  - `: new -s mysession`: Start a session named _mysession_.

### Managing Sessions
- **Kill the current session**:  
  `: kill-session`
- **Kill a specific session**:  
  ```bash
  $ tmux kill-ses -t mysession
  ```
- **Kill all sessions but the current one**:  
  ```bash
  $ tmux kill-session -a
  ```
- **Kill all but a specific session**:  
  ```bash
  $ tmux kill-session -a -t mysession
  ```

### Renaming and Detaching
- **Rename session**: `Ctrl + b $`
- **Detach from session**: `Ctrl + b d`
- **Detach others in the session**:  
  `: attach -d`

### Viewing and Switching Sessions
- **List all sessions**:  
  ```bash
  $ tmux ls
  $ tmux list-sessions
  ```
- **Attach to a session**:  
  ```bash
  $ tmux a
  $ tmux attach
  $ tmux attach-session
  ```
- **Attach to a specific session**:  
  ```bash
  $ tmux a -t mysession
  $ tmux attach -t mysession
  ```
- **Session navigation**:  
  - `Ctrl + b s`: Show all sessions  
  - `Ctrl + b (`: Previous session  
  - `Ctrl + b )`: Next session

---

## 🪟 Windows

### Creating and Renaming
- **Start a session with a named window**:  
  ```bash
  $ tmux new -s mysession -n mywindow
  ```
- **Create a new window**: `Ctrl + b c`
- **Rename current window**: `Ctrl + b ,`

### Managing Windows
- **Close current window**: `Ctrl + b &`
- **List all windows**: `Ctrl + b w`
- **Switch windows**:  
  - Previous: `Ctrl + b p`  
  - Next: `Ctrl + b n`  
  - By number: `Ctrl + b 0 ... 9`  
  - Last active: `Ctrl + b l`

### Reordering Windows
- **Swap windows**:  
  ```bash
  : swap-window -s 2 -t 1
  ```
- **Move window to the left**:  
  ```bash
  : swap-window -t -1
  ```
- **Reposition windows**:  
  ```bash
  : move-window -s src_window -t target_window
  ```
- **Remove gaps in window numbers**:  
  ```bash
  : move-window -r
  ```

---

## 🔲 Panes

### Splitting Panes
- **Split vertically**: `Ctrl + b %`  
  `: split-window -h`
- **Split horizontally**: `Ctrl + b "`  
  `: split-window -v`

### Navigating Panes
- **Switch to another pane**: `Ctrl + b o`
- **Show pane numbers**: `Ctrl + b q`
- **Switch to pane by number**: `Ctrl + b q 0 ... 9`
- **Toggle pane zoom**: `Ctrl + b z`

### Moving and Resizing
- **Move pane**:  
  - Left: `Ctrl + b {`  
  - Right: `Ctrl + b }`
- **Resize pane**:  
  - Adjust height: `Ctrl + b +`  
  - Adjust width: `Ctrl + b Ctrl +`

### Managing Panes
- **Close current pane**: `Ctrl + b x`
- **Convert pane to a window**: `Ctrl + b !`
- **Synchronize panes**:  
  ```bash
  : setw synchronize-panes
  ```

---

## 📋 Copy Mode

### Navigation and Selection
- **Enter copy mode**: `Ctrl + b [`
- **Scroll**:  
  - Up: `Ctrl + b PgUp`  
  - Down: Arrow keys
- **Move cursor**:  
  - Left: `h`  
  - Right: `l`  
  - Up: `k`  
  - Down: `j`
- **Word navigation**:  
  - Forward: `w`  
  - Backward: `b`
- **Search**:  
  - Forward: `/`  
  - Backward: `?`

### Copy and Paste
- **Start selection**: `Spacebar`
- **Copy selection**: `Enter`
- **Paste buffer**: `Ctrl + b ]`

---

## ⚙️ Miscellaneous

- **Command mode**: `Ctrl + b :`
- **Enable mouse mode**:  
  ```bash
  : set mouse on
  ```
- **List all key bindings**:  
  ```bash
  $ tmux list-keys
  Ctrl + b ?
  ```

---

## 🔍 Help and Info

- **Show all sessions, windows, and panes**:  
  ```bash
  $ tmux info
  ```

### Features of this version:
1. **Emojis**: Enhance readability and visual structure.
2. **Consistent formatting**: Commands and keybindings are highlighted using inline code blocks.
3. **Sections**: Clear separation of sections for Sessions, Windows, Panes, etc.
4. **Compact yet detailed**: Includes all key commands while remaining user-friendly.
