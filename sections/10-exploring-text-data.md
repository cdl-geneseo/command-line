← [Pipes](09-pipes.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Interlude](11-interlude.md) →

---

# 10. Exploring Text Data

So far the only text file we've been working with is our cheat sheet. Now, this is where the command line can be a very powerful tool: let's try working with a large text file, one that would be too large to work with by hand.

Let's download the file we're going to work with:

[Download `walden.txt`](https://raw.githubusercontent.com/cdl-geneseo/command-line/fall-20-workshop/files/walden.txt) (To download the file rather than open it in your browser window, you may need to right-click and "Save File As ...")

Our file contains the text of Henry David Thoreau's *Walden*, obtained from [Gutenberg.org](https://www.gutenberg.org/files/205/205-0.txt) and cleaned up to remove another Thoreau text from the file ("Civil Disobedience") and the boilerplate language that Gutenberg includes at the top and bottom of every file. 

## Move Command

Once the file is downloaded, move it from your `Downloads` folder to the `projects` folder on your desktop—either through the command line or by dragging and dropping in the GUI. Since this is indeed a command line workshop, you should try the former!

To move this file using the command line, you first need to navigate to your `Downloads` folder where that file is saved. Then type the `mv` command followed by the name of the file you want to move and then the file path to your `projects` folder on your desktop, which is where you want to move that file to (note that `~` refers to your home folder):

```console
$ mv walden.txt ~/Desktop/projects/
```

You can then navigate to that `projects` folder and use the `ls` command to check that the file is now there.

## Viewing Data in the Command Line

Try using `cat` to look at the data. You'll find it all goes by too fast to get any sense of it. (You can click <kbd>control</kbd> + <kbd>c</kbd> on your keyboard to cancel the output if it's taking too long.)

Instead, let's use another tool, the `less` command, to get the data one page at a time:

```console
$ less walden.txt
...
```

`less` gives you a paginated view of the data; it will show you contents of a file or the output from a command or string of commands, page by page.

To view the file contents page by page, you may use the following keyboard shortcuts (that should work on Windows using Git Bash or on macOS terminal):

Click the <kbd>f</kbd> key to view forward one page, or the <kbd>b</kbd> key to view back one page.

Once you're done, click the <kbd>q</kbd> key to return to the command line.

Let's try two more commands for viewing the contents of a file:

```console
$ head walden.txt
...

$ tail walden.txt
...
```
These commands print out the very first (the "head") and very last (the "tail") sections of the file, respectively.

← [Pipes](09-pipes.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Interlude](11-interlude.md) →