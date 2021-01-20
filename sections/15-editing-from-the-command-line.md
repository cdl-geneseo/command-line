← [Title](file.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Title](file.md) →

---
# 15. Editing from the command line

You've already seen that you can look inside plain text files from the command line using commands like `cat` and `less`. It's also possible to edit plain text files directly in a terminal window without launching VS Code or another external plain-text editing application. 

If you spend enough time on the command line, eventually you'll find yourself in a situation where you'll need to know how to do this, so let's take a moment to see how to perform a few of the most basic editing operations in two of the most common command-line editors, Vim and Nano.

## Vim

Create a new file or open an existing one:

```$ vim filename.txt
```
The editor will open in the terminal. To begin editing, type the letter `i` (for "insert"). This puts your editor in "Insert" mode.

Type a line of text: for example, 

```Hello, World!
```
To save the content you've just added to the file, first hit `esc` (Escape) to exit "Insert" mode, then type `:w`, then hit `return/enter`. You'll get some feedback at the bottom of your terminal window letting you know that you've successfully "written" content to the file.

Type `:q` (for "quit") and hit `return/enter` to close the file. You'll find yourself back at the command-line prompt.

If you type

```cat filename.txt
```
you can confirm that you saved the file content successfully.

Suppose you want to re-enter the file and add a line? 

```$ vim filename.txt
```
Don't type `i` yet. (If you did, hit `esc`.) You'll see your cursor sitting at the top of the file. Notice that you can't simply mouse to the end of the line and click to drop your cursor there. Nor can you create a new line beneath the existing one by hitting `return`.

To relocate your cursor, you can use your keyboard's arrow keys or certain of the letter keys. For example, `l` moves your cursor one character to the right, while `h` moves it one character to the left. You can move up and down in a file using `k` and `j`, respectively. You can use `w` to move forward one word at a time and `b` to move back one word at a time. Use `)` and `(` to move forward and back, respectively, one sentence at a time.

Let's add a little more text. Move the cursor where you'd like it, then type `i` to enter "Insert" mode. (Once you do this, the letter keys will no longer be available for navigation until you exit "Insert" mode with `esc`, but you can still navigate with your arrow keys.)

Type some additional text.

To save yourself some time, after hitting `esc` you can save and quit by combining the two commands we used above: `:wq`, followed by `return/enter`.

It takes a while to get the hang of Vim's keyboard commands, but once you do, it will seem much less intimidating. There are additional commands that let you perform standard editing tasks such as cut, copy, paste, and undo. One useful feature of Vim is its ability to highlight syntax in documents that include markup (HTML or XML, for example) or programming instructions. Typing `:syntax on` will turn this feature on.

## Nano

You may find Nano a little more user-friendly than Vim. Create a new text file by typing

```$ nano newfilename.txt
```
Or, if you prefer, re-enter the file you just edited in Vim:

```$ nano filename.txt
```
With Nano, you can start moving around in the file and typing right away; no need to switch into a special "Insert" mode.

In Nano, as in Vim, you move your cursor using the keyboard. Type `ctrl-f` to move forward one character, `ctrl-b` to move back one character, `ctrl-n` to move down to the next line and `ctrl-p` to move up to the previous line. Move to the end of a line with `ctrl-e` and to the beginning of a line with `ctrl-a`.

Nano conveniently displays a handy list of commands right at the bottom of the editor window.

Add some text to your file, then hit `ctrl-o`, followed by `enter/return`. As in Vim, you'll see feedback at the bottom of the window, such as "[Wrote one line.]"

Type `ctrl-x` to exit and close the file in one move.

Again, you can confirm the effects of your editing by using `cat` or `less` followed by the file name right at the command line, or by opening the file in VS Code.

## Final thought: the payoff of plain text editing

Notice that you can use Vim, Nano, and VS Code interchangeably on any plain text file. Moving between them isn't at all like moving between, say, Google docs and Microsoft Word. Google and Word documents contain all sorts of proprietary code that's not visible to you when you're working in them and that differs from one format to the other; as a result, moving from between formats can produce unpredictable results.

---

← [Title](file.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Title](file.md) →