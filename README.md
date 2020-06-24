# Vim Cheat Sheet 🤓

Vim Cheat Sheet, useful commands compatible with [VSCodeVim](https://github.com/VSCodeVim/Vim) for Microsoft Visual Studio Code.

## Introduction

In this document, I'll share with you my Vim learnings, listing everyday commands, nouns, and movements I found useful to be more productive in everyday coding. Vim is a powerful text editor, this document is not exhaustive.

## Vim as Language

Vim commands are formed from a combination of verbs and targets. The targets could be objects (words, sentences, paragraphs, lines, the contents of parentheses) or movements (jump to the end of a word, jump to end of the paragraph, jump forward until the letter ‘e’, etc). Forming objects generally involves the use of a modifier. You can also add a count to perform the action count times.

### Commands

|    |                                                                     |
|----|---------------------------------------------------------------------|
| v  | visual                                                              |
| c  | change                                                              |
| d  | delete (remove from the document and put in buffer)                 |
| dd | delete current line                                                 |
| y  | yank/copy                                                           |
| yy | yank/copy the line)                                                 |
| i  | enter insert mode                                                   |
| I  | enter insert mode at the beginning of the line                      |
| v  | enter visual mode                                                   |
| V  | enter visual line (selects the current line in one keystroke)       |
| p  | paste the buffer after the cursor                                   |
| P  | paste the buffer before the cursor                                  |
| r  | replace the character under the cursor with [char]                  |
| s  | delete the character under the curser and puts you into insert mode |
| x  | delete the character under the cursor                               |
| u  | undo the last command                                               |
| a  | append and enter insert mode after the carat                        |
| A  | append to line (enter insert mode at the end of the line)           |
| o  | open a line after the current one and enter insert mode             |
| O  | open a line before the current one and enter insert mode            |

### Modifiers

|   |                                             |
|---|---------------------------------------------|
| i | inside                                      |
| a | around                                      |
| t | till...finds a character                    |
| f | find... like till except including the char |
| / | search...find a string/regex                |

### Targets (Text objects)

|   |                        |
|---|------------------------|
| w | word                   |
| s | sentence               |
| p | paragraph              |
| b | block/parentheses      |
| t | tag, works for html/xm |

## Nouns/Movements

Nouns or movements are commands for moving within the document or representing an area within a document.

|            |                                                                       |
|------------|-----------------------------------------------------------------------|
| h, j, k, l | move, equivalent to the arrow keys left, down, up, right              |
| H          | move to the top of screen                                             |
| M          | move to the middle of screen                                          |
| L          | move to the bottom of screen                                          |
| zz         | scroll the line with the cursor to the center of the screen           |
| zt         | scroll the line with the cursor to the top                            |
| zb         | scroll the line with the cursor to the bottom                         |
| Ctrl-D     | move half-page down                                                   |
| Ctrl-U     | move half-page up                                                     |
| Ctrl-B     | page up                                                               |
| Ctrl-F     | page down                                                             |
| 0          | move to the very beginning of the current line                        |
| ^          | move to the first non-whitespace character on the line                |
| $          | move to the end of the line                                           |
| w, b       | move to the next/previous word                                        |
| W, B       | as w/b only Words are bigger                                          |
| ), (       | move to the next/previous sentence                                    |
| }, {       | move to the next/previous paragraph                                   |
| /[regexp]  | like t but instead of finding a character, it finds a regexp          |
| %          | jump to the matching parenthesis (vim understands nested parenthesis) |
| _          | move to the current line (useful for making commands line-based)      |
| #[char]    | jump to the previous instance of the word under [char]                |
| >>         | indent line                                                           |
| <<         | outdent line                                                          |
| *[char]    | jump to the next instance of the word under [char]                    |
| ddp / ddkP | are common commands to move a line one down / up                      |

## Useful

|          |                                                                                                                                                           |
|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| vi[char] | visualize all content inside that characters excluding delimiter                                                                                          |
| va[char] | visualize all content inside that characters including delimiter                                                                                          |
| vi{      | select all content inside curly braces excluding braces                                                                                                   |
| va{      | select all content inside curly braces including braces                                                                                                   |
| viw      | select world under the cursor                                                                                                                             |
| vit      | visually select text in a tag                                                                                                                             |
| vat      | visually select text around a tag                                                                                                                         |
| vap      | visually select paragraph under cursor                                                                                                                    |
| Ctrl-R   | redo the last undo (sidenote: in vim undo/redo forms a tree, changes aren’t lost)                                                                         |
| Ctrl-[   | exit insert mode                                                                                                                                          |
| Ctrl-c   | exit insert mode                                                                                                                                          |
| gc       | toggles line comment, example `gcc` to toggle line comment for the current line and `gc2j` to toggle line comments for the current line and the next line |
| gC       | toggles block comment, example `gCi` to comment out everything within parenthesis                                                                         |
| :sp      | spit current document in two horizontally                                                                                                                 |
| :vs      | spit current document in two vertically                                                                                                                   |
| Ctrl-ww  | window switching                                                                                                                                          |
| ciw      | change inner word will change the whole word under the cursor                                                                                             |
| cw       | change the word from the current cursor position                                                                                                          |
| /        | enter regex search mode                                                                                                                                   |
| n        | find the next instance of the search term                                                                                                                 |
| N        | find the previous instance of the search term                                                                                                             |
| .        | repeat last change (extremely powerful)                                                                                                                   |
| ^ or 0   | move to the beginning of the line                                                                                                                         |
| Shift+0  | move to the end of the line                                                                                                                               |
| Shift+i  | move to the beginning of the line and switch to insert mode                                                                                               |

## Registers

Registers in Vim let you run actions or commands on text stored within them. To access a register, you type `a` before a command, where a is the name of a register.
Please, note some of these commands are not supported by VSCodeVim yet.

|      |                                                                                       |
|------|---------------------------------------------------------------------------------------|
| :reg | access all currently defined registers                                                |
| "kyy | copy the current line into register `k`                                               |
| "Kyy | append to a register by using a capital letter                                        |
| "kp  | paste value of the register                                                           |
| "+p  | paste from system clipboard on Linux                                                  |
| "*p  | paste from system clipboard on Windows (or from "mouse highlight" clipboard on Linux) |

## Others

|              |                                                                      |
|--------------|----------------------------------------------------------------------|
| `.`          | the dot, command repeats the last change made in normal mode         |
| dat          | delete the current tag (and all its content)                         |
| f[character] | find character and move cursor at that position                      |
| t[character] | find character and move cursor at one position before                |
| vi[          | visual select inside `[`                                             |
| i[character] | expand selection to that character, similar including `a{character}` |
| gt           | move the cursor to next tab                                          |
| gT           | move the cursor to prior tab                                         |
| nnngt        | numbered tab                                                         |
| :tabonly     | close all tabs and keep open only the focused one                    |
| :split       | split into two windows, top half and bottom half                     |
| :sp          | same as :split                                                       |
| :vsplit      | split into two windows, left and right                               |
| :vsp         | same as :vsplit                                                      |

Notes:
You can then use Ctrl-W direction to switch windows (where direction is one of the normal hjkl cursor movement keys, or the arrow keys)
The focus is on the new split initially. To move between splits first press Ctrl-w.

|        |                                                                                   |
|--------|-----------------------------------------------------------------------------------|
| Ctrl-y | move the screen up one line                                                           |
| Ctrl-e | move the screen down one line                                                         |
| Ctrl-u | move cursor & screen up ½ page                                                    |
| Ctrl-d | move cursor & screen down ½ page                                                  |
| Ctrl-b | move the screen up one page, cursor to the last line                                  |
| Ctrl-f | move the screen down one page, cursor to the first line                               |
| Ctrl-y | and Ctrl-e only change the cursor position if it would be moved off-screen        |
| zt     | move current line to the top of the screen                                        |
| zb     | move current line to the bottom of the screen                                     |
| t      | till, example dt. (delete till dot) or df.(delete till dot included)              |
| CTRL-O | retrace your movements in file in backward                                        |
| CTRL-I | retrace your movements in file in forwards                                        |
| J      | joins the line the cursor is on with the line below                               |
| viwp   | visual select inner word and paste (change a selected word using current buffer ) |

Notes:
The quickest way to retrace your movements is to hit either: two apostrophes `''` or two backticks ````.
The difference is that the backtick goes to the same location on the line, whereas the apostrophe goes to the start of the line. On a UK keyboard, the apostrophe is more accessible, so I tend to use that one. There are loads of useful marks like this, see :help mark-motions.

Move to the end of the line in normal mode in VIM: Jump to last nonblank `g_` or use `$` which moves to the last character on the line.

### Deleting

|     |                                                                                                     |
|-----|-----------------------------------------------------------------------------------------------------|
| dw  | delete from the current cursor position to the beginning of the next word character                 |
| d$  | delete from the current cursor position to the end of the current line ((note that's a dollar sign) |
| D   | as d$                                                                                               |
| dtX | delete forward up to character 'X'                                                                  |
| dfX | delete forward through character 'X'                                                                |
| dTX | delete backward up to character 'X'                                                                 |
| dFX | delete backward through character 'X'                                                               |
| :%d | delete all content of the document                                                                  |

### Change case

|      |                                                   |
|------|---------------------------------------------------|
| ~    | changes the case of current character             |
| guu  | change the current line from upper to lower           |
| gUU  | change the current line from lower to upper           |
| guw  | change to the end of current WORD from upper to lower |
| guaw | change all of the current WORD to lower.              |
| gUw  | change to the end of the current WORD from lower to upper |
| gUaw | change all of the current WORD to upper               |
| g~~  | invert case to entire line                        |
| guG  | change to lowercase until the end of document     |

## Interesting resources

[Using marks](http://vim.wikia.com/wiki/Using_marks)

[vim + tmux](https://www.youtube.com/watch?v=5r6yzFEXajQ&t=1269s)

[Mastering the Vim Language](https://www.youtube.com/watch?v=wlR5gYd6um0)

[All the right moves](https://vim.fandom.com/wiki/All_the_right_moves)

[Graphical cheat sheet](https://eggplant.pro/blog/wp-content/uploads/2016/12/vi-vim-tutorial.pdf)
