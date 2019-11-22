# Vim

## What's a quick way to comment/uncomment lines in Vim?
https://stackoverflow.com/questions/1676632/whats-a-quick-way-to-comment-uncomment-lines-in-vim

For those tasks I use most of the time [block selection](http://vimdoc.sourceforge.net/htmldoc/visual.html).

Put your cursor on the first # character, press Ctrl+V (or CtrlQ for gVim), and go down until the last commented line and press x, that will delete all the # characters vertically.

For commenting a block of text is almost the same:

1. First, go to the first line you want to comment, press Ctrl+V. This will put the editor in the VISUAL BLOCK mode.
2. Then using the arrow key and select until the last line
Now press Shift+I, which will put the editor in INSERT mode and then press #. 
3. This will add a hash to the first line.
4. Then press Esc (give it a second), and it will insert a # character on all other selected lines.

[Search and replace](https://vim.fandom.com/wiki/Search_and_replace)
- 