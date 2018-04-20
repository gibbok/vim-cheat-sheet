# Vim Cheat Sheet
Vim cheat sheet, useful commands compatible with `vscodevim` for Microsoft Visual Studio Code.

verbs: v (visual), c (change), d (delete), y (yank/copy). these are the most important. there are others

modifiers: i (inside), a (around), t (till..finds a character), f (find..like till except including the char), / (search..find a string/regex)

text objects: w (word), s (sentence) p (paragraph) b (block/parentheses), t (tag, works for html/xml)



## Commands

Vim commands are formed from a combination of verbs and targets.The targets could be objects (words, sentences, paragraphs, lines, the contents of parentheses) or movements (jump to end of word, jump to end of paragraph, jump forward until the letter ‘e’, etc). Forming objects generally involves the use of a modifier. You can also add a count to perform the action count times.





## Verbs

| Command | Use | 
| - | - | 
| i | insert - enter insert mode |
| v | enter visual mode |
| V | enter visual line (selects the current line in one key stroke) |
| viw | select world under the cursor |
| a | append - enter insert mode after the carat | 
| I | enter insert mode at the beginning of the line | 
| A | append to line (enter insert mode at the end of the line) | 
| o | open a line after the current one and enter insert mode |
| O | open a line before the current one and enter insert mode |
| d[target] | delete (remove from the document and put in buffer) |
| dd | delete current line |
| y[target] | yank (copy) |
| yy | yank (copy the line) |
| p | paste the buffer after the cursor |
| P | paste the buffer before the cursor |
| c[target] | change (delete and then enter insert mode) |
| ciw | change inner word will change the whole word under the cursor |
| cw | change the word from the current cursor position |
| s | deletes the character under the curser and puts you into insert mode |
| r[char] | replace the character under the cursor with [char] |
| x | delete the character under the cursor |
| u | undo the last command |
| Ctrl-R | redo the last undo (sidenote: in vim undo/redo forms a tree, changes aren’t lost) |
| / | enter regex search mode |
| n | find the next instance of the search term |
| N | find the previous instance of the search term |
| . | repeat last change (extremely powerful) |
| gc | toggles line comment, example `gcc` to toggle line comment for current line and `gc2j` to toggle line comments for the current line and the next line |
| gC | toggles block comment, example `gCi` to comment out everything within parenthesis.
| vit | visually select text in a tag |
| vat | visually select text around a tag |
| ^ or 0 | move to the beginning of the line |
| shift+0 | move to the end of the line | 
| shift+i | move to the beginning of the line and switch to insert mode |
| $ | move to the end of the line |
| vap | visually select paragraph under cursor | 

## Nouns/Movements

Nouns or movements are commands for moving within the document or representing an area within a document.

| Command | Use | 
| - | - | 
| h, j, k, l | equivalent to the arrow keys left, down, up, right |
| H | move to top of screen |
| M | move to middle of screen |
| L | move to bottom of screen |
| zz | scroll the line with the cursor to the center of the screen |
| zt | scroll the line with the cursor to the top |
| zb | scroll the line with the cursor to the bottom |
| Ctrl-D | move half-page down |
| Ctrl-U | move half-page up |
| Ctrl-B | page up |
|Ctrl-F | page down |
| 0 | move to the very beginning of the current line |
| ^ | move to the first non-whitespace character on the line |
| $ | move to the end of the line |
| w, b | move to the next/previous word |
| W, B | as w/b only Words are bigger |
| ), ( | move to the next/previous sentence |
| }, { | move to the next/previous paragraph |
| /[regexp] | like t but instead of finding a character it finds a regexp |
| % | jump to the matching parenthesis (vim understands nested parenthesis) |
| _ | move to the current line (useful for making commands line-based) |
| #[char] | jump to the previous instance of the word under [char] |
| >> or << | indent the line |
| *[char] | jump to the next instance of the word under [char] |
| ddp / ddkP | are common commands to move a line one down / up |



Registers in Vim let you run actions or commands on text stored within them. To access a register, you type "a before a command, where a is the name of a register. If you want to copy the current line into register k, you can type

"kyy

Or you can append to a register by using a capital letter

"Kyy

You can then move through the document and paste it elsewhere using

"kp

To paste from system clipboard on Linux

"+p

To paste from system clipboard on Windows (or from "mouse highlight" clipboard on Linux)

"*p

To access all currently defined registers type

:reg
