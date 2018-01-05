# Vim Cheat Sheet
Vim cheat sheet, useful commands compatible with `vscodevim` for Microsoft Visual Studio Code.

| Command | Use | 
| - | - | 
| i | insert - enter insert mode |
| a | append - enter insert mode after the carat | 
| I | enter insert mode at the beginning of the line | 
| A | append to line (enter insert mode at the end of the line) | 
| o | open a line after the current one and enter insert mode |
| O | open a line before the current one and enter insert mode |
| d[target] | delete (remove from the document and put in buffer) |
| y[target] | yank (copy) |
| p | paste the buffer after the cursor |
| P | paste the buffer before the cursor |
| c[target] | change (delete and then enter insert mode) |
| r[char] | replace the character under the cursor with [char] |
| x | delete the character under the cursor |
| u | undo the last command |
| Ctrl-R | redo the last undo (sidenote: in vim undo/redo forms a tree, changes aren’t lost) |
| / | enter regex search mode |
| n | find the next instance of the search term |
| N | find the previous instance of the search term |
| . | repeat last change (extremely powerful) |


- Put the cursor on a word and hit the * key and you will jump to the next instance of that word.

- The # key does the same but jumps to the previous instance of the word.




