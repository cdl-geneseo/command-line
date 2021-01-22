← [Editing from the Command Line](12-editing-from-the-command-line.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Analyzing Text Data](14-analyzing-text-data.md) →

---

# 13. Exploring Text Data

## Obtaining text data from the web

Using the command line, you can download texts and other data directly from the command line. One way to do this is to use `curl`. "Curl," sometimes written "cURL," is an acronym for "client URL." If you point `curl` at a file located at a URL on the web, `curl` will stream the content of that file to your shell, where it can be printed to your screen, piped as input to another command, or written to a file that you can save to disk. 

One use for `curl` is to save web pages in HTML format for offline viewing. How well this works in practice will depend on how the web page in question has been coded. Images and links in many web pages may be absent or non-functional when viewed this way, but the text content is usually readable. For example, try using `curl` on the page you're looking at rignt now. Copy the URL from your browser's location bar, and paste that URL into a terminal window after the `curl` command, adding a re-direct to write the page contents to a file. (*NB*: Be sure to add the `.html` extension to the end of the file so that your browser knows to display the file as it would on the web.)

```
$ curl https://github.com/cdl-geneseo/command-line/blob/fall-20-workshop/sections/12-searching-text-data.md > searching-text-data.html
```
Depending on how your computer's operating system preferences are set, you may be able to open this file by simply double-clicking it in the GUI. If doing that opens the file in VS Code or another text editor, try right-clicking the file icon and telling your computer to open the file in, say, Firefox or Safari.

If you look in your browser's location bar, you won't see a web address but rather a path to the file's location on your computer. It might look something like this:

```
file:///Users/schacht/Desktop/searching-text-data.html
```

If you're connected to the internet, the page will look pretty much the same as it does on the web. But if you disconnect from the internet and refresh the page, it will look quite different; images will be missing, and much of the text styling will be lost. But the important content is still there and readable.

On pages that contain minimal styling and few or no images, what you see offline will differ very little from what you see online. For example, compare how Neal Stephenson's essay, ["In the Beginning ... Was the Command Line"](http://cristal.inria.fr/~weis/info/commandline.html) looks on the web to what you see if you `curl` the page, save it to a file (remember to give it the `.html` extension!) and display the saved page in your browser while offline.

So far the only text file we've been working with is our cheat sheet. Now, this is where the command line can be a very powerful tool: let's try working with a large text file, one that would be too large to work with by hand.

Let's download the file we're going to work with:

[Download `walden.txt`](https://raw.githubusercontent.com/cdl-geneseo/command-line/fall-20-workshop/files/walden.txt) (To download the file rather than open it in your browser window, you may need to right-click and "Save Link As ...". On a Mac laptop, which doesn't have a dedicated button for right-clicking, press the trackpad while holding down the <kbd>control</kbd> key. If a dialog pops up asking where to save the file, save it to your `Downloads` folder.)

Our file contains the text of Henry David Thoreau's *Walden*, obtained from [Gutenberg.org](https://www.gutenberg.org/files/205/205-0.txt) and cleaned up to remove another Thoreau text from the file ("Civil Disobedience") and the boilerplate language that Gutenberg includes at the top and bottom of every file. 

## Move Command

Once the file is downloaded, move it from your `Downloads` folder to the `projects` folder on your desktop—either through the command line or by dragging and dropping in the GUI. Since this is a command line workshop, why not try the former?

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

← [Editing from the Command Line](12-editing-from-the-command-line.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Analyzing Text Data](14-analyzing-text-data.md) →