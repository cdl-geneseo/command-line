← [Title](file.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Title](file.md) →

---
# 15. Editing from the command line

You've already seen that you can look inside plain text file from the command line using commands like `cat` and `less`. It's also possible to edit plain text files directly in a terminal window without launching VS Code or some other external plain-text editing application. 

If you spend enough time on the command line, eventually you'll find yourself in a situation where you'll need to know how to do this, so let's take a moment to see how to perform the most basic editing operations in two of the most popular command-line editors, Vim and Nano.

## Vim

Create a new file or open an existing one:

```
$ vim filename.txt
```

The editor will open in the terminal. To begin editing, type the letter `i` (for "insert"). This puts your editor in "Insert" mode.

Type a line of text: for example, 

```
Hello, World!
```
To save the content you've just added to the file, first hit `esc` (Escape) to exit "Insert" mode, then type `:w`, then hit `return/enter`. You'll get some feedback at the bottom of your terminal window letting you know that you've successfully "written" content to the file.

Type `:q` (for "quit") and hit `return/enter` to close the file.

Suppose you want to re-enter the file and add a line? 

```
$ vim filename.txt
```
Again, type "i" to insert text. You'll get a cursor at the top of the file. How do you start a new line? Notice that you can't simply move your mouse to the end of the line and drop your cursor there.

Instead, use the right-arrow key at the bottom right of your keyboard to move the cursor to the end of the line, then hit `enter/return` to start a new line. 

There are more efficient ways to move around inside files using Vim. For example, when you're not in "insert" mode, you can move forward a word at a time by using  `w` key, back a word at a time using `b`, forward a sentence at a time using `)` and back a sentence at a time using `(`. 

Type some additional text.

To save yourself some time, after hitting `esc` you can save and quit by combining the two commands we used above: `:wq`, followed by `return/enter`

## Nano

The Nano editor is a bit more intuitive than Vim. Create a new file by typing

```
$ nano newfilename.txt
```

Or, if you prefer, re-enter the file you were just working on using Vim:

```
$ nano filename.txt
```
With Nano, you can start moving around in the file and typing right away; no need to switch into "Insert" mode.

You can easily move to the end of the line you're on by typing `ctrl-e`, and move back to the beginning of the line with `ctrl-a`.

You'll also see a handy list of commands right at the bottom of the screen.

Add some text to the file, then hit `ctrl-o`, followed by `enter/return`. As in Vim, you'll see feedback at the bottom of the window, such as "[Wrote one line.]"

Type `ctrl-x` to exit and close the file.

You can see the effects of your editing by opening the file in VS Code or by typing `cat` or `less` followed by the file name at the command line.

---

← [Title](file.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Title](file.md) →