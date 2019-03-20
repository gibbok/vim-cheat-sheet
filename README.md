# Vim Cheat Sheet
Vim cheat sheet, useful commands compatible with `vscodevim` for Microsoft Visual Studio Code.

## Vim as Language


### Commands
Vim commands are formed from a combination of verbs and targets.The targets could be objects (words, sentences, paragraphs, lines, the contents of parentheses) or movements (jump to end of word, jump to end of paragraph, jump forward until the letter ‘e’, etc).
Forming objects generally involves the use of a modifier. You can also add a count to perform the action count times.

| Verbs | Use | 
| - | - | 
| v | visual |
| c | change |
| d | delete (remove from the document and put in buffer) |
| dd | delete current line |
| y | yank/copy |
| yy | yank/copy the line) |
| i | enter insert mode |
| I | enter insert mode at the beginning of the line |
| v | enter visual mode |
| V | enter visual line (selects the current line in one key stroke) |
| p | paste the buffer after the cursor |
| P | paste the buffer before the cursor |
| r | replace the character under the cursor with [char] |
| s | deletes the character under the curser and puts you into insert mode |
| x | delete the character under the cursor |
| u | undo the last command |
| a | append - enter insert mode after the carat | 
| A | append to line (enter insert mode at the end of the line) | 
| o | open a line after the current one and enter insert mode |
| O | open a line before the current one and enter insert mode |


| Modifiers | Use | 
| - | - |
| i | inside |
| a | around |
| t | till..finds a character |
| f | ind..like till except including the char |
| / | search..find a string/regex |

| Text objects | Use | 
| - | - |
| w | word |
| s | sentence |
| p | paragraph |
| b | block/parentheses |
| t | tag, works for html/xm |



## Useful

| Command | Use | 
| - | - | 
|vi[char]| visualize all content inside that cahracters excluding delimiter |
|va[char]| visualize all content inside that cahracters including delimiter |
| vi{ | select all content inside curly braces excluding braces |
| va{ | select all content inside curly braces including braces |
| viw | select world under the cursor |
| vit | visually select text in a tag |
| vat | visually select text around a tag |
| Ctrl-R | redo the last undo (sidenote: in vim undo/redo forms a tree, changes aren’t lost) |
| Ctrl-[ | exit insert mode |
| Ctrl-c | exit insert mode |
| gc | toggles line comment, example `gcc` to toggle line comment for current line and `gc2j` to toggle line comments for the current line and the next line |
| gC | toggles block comment, example `gCi` to comment out everything within parenthesis |
| :sp | spit current document in two |
| Ctrl-ww | window switching |


## Verbs

| Command | Use | 
| - | - | 
| ciw | change inner word will change the whole word under the cursor |
| cw | change the word from the current cursor position |
| / | enter regex search mode |
| n | find the next instance of the search term |
| N | find the previous instance of the search term |
| . | repeat last change (extremely powerful) |
| ^ or 0 | move to the beginning of the line |
| Shift+0 | move to the end of the line | 
| Shift+i | move to the beginning of the line and switch to insert mode |
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
| Ctrl-F | page down |
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
| >> | indent line |
| << | outdent line |
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


------------

The "." command repeats the last change made in normal mode. For example, if you press dw to delete a word, you can then press . to delete another word (. is dot, aka period or full stop).


http://vim.wikia.com/wiki/Using_marks



`dat` = delete current tag (and all its content)

`f[caracther]` = find character and move cursor at that position
`t[caracther]` = find character and move cursor at one position before

`H` go to higher part of the screen
`M` go to the midle part of the screen
`L` go to the lower part of the screen


https://github.com/gibbok/vim-cheat-sheet


f{character}
find and move character to target

;
move to next command

t{character}
find and move one character before target

`vi[`
visual select inside [
if in visual more we select
`i{character}` we can expand the selection to that character, similar including `a{character}`



Next tab: gt

Prior tab: gT

Numbered tab: nnngt
Close all tabs and keep open only the focused one: :tabonly

:split (split into two windows, top half and bottom half) and :vsplit (left and right) commands. You can then use Ctrl-W direction to switch windows (where direction is one of the normal hjkl cursor movement keys, or the arrow keys)
A shortcut for a horizontal split is :sp, with the vertical shortcut being :vsp

Focus is in the new split initially. To move between splits first press Ctrl-w 

Ctrl-y Moves screen up one line
Ctrl-e Moves screen down one line
Ctrl-u Moves cursor & screen up ½ page
Ctrl-d Moves cursor & screen down ½ page
Ctrl-b Moves screen up one page, cursor to last line
Ctrl-f Moves screen down one page, cursor to first line
Ctrl-y and Ctrl-e only change the cursor position if it would be moved off screen.

zt - move current line to the top of the screen

zb - move current line to the bottom of the screen

t = till
example: dt. (delete till dot)
or df.(delete till dot included)
You can remember these commands as `find` and `t`ill. 


https://www.youtube.com/watch?v=5r6yzFEXajQ&t=1269s

CTRL-O : Retrace your movements in file in backwards.

CTRL-I : Retrace your movements in file in forwards.
From the vim help files:


The quickest way is to hit either:

(two apostrophes) or
```
''
```

(two backticks):

```
``
```

Note that the difference is that the backtick goes to the same location on the line, whereas the apostrophe goes to the start of the line. On a UK keyboard, the apostrophe is more accessible, so I tend to use that one. There are loads of useful marks like this, see :help mark-motions.

---
The command dw will delete from the current cursor position to the beginning of the next word character. The command d$ (note, that's a dollar sign, not an 'S') will delete from the current cursor position to the end of the current line. D is a synonym for d$.


https://www.youtube.com/watch?v=wlR5gYd6um0

To delete forward up to character 'X' type dtX

To delete forward through character 'X' type dfX

To delete backward up to character 'X' type dTX

To delete backward through character 'X' type dFX
