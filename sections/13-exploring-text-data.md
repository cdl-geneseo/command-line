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

You can use `curl` to obtain text data from the web other than HTML files — for example, you can use it to download data files in a "flat" format such as `.csv` or `.tsv`, and you can use it to download books and other text content available on the web in `.txt` files. 

Another, more powerful and flexible, command-line tool for downloading web content is `wget`. We won't use it here because it may not be installed on your system. 

## Obtaining content from Gutenberg.org

[Guutenberg.org](https://www.gutenberg.org) is a terrific source of public domain texts. The site makes most texts available in multiple formats, including HTML and plain text.

Let's say we wanted to grab ourselves a copy of Henry David Thoreau's *Walden*. Here's how we could do that.

Type

```
$ curl https://www.gutenberg.org/files/205/205-0.txt
```
and hit `return/enter`. What happens? Gutenberg.org's edition of *Walden, and On The Duty Of Civil Disobedience* is streamed to your terminal. But like a video that you stream on YouTube, this text stream isn't saved to your disk. It's not in a file anywhere, and if you end your shell session, you'll lose the content. To save it, you need to re-direct the streamed content to a file, as we did with the websites like so:

```
$ curl https://www.gutenberg.org/files/205/205-0.txt > walden-gutenberg.txt
```
What you saw in the stream in your terminal window and in the file you just saved is identical to what you would see if you simply went to <https://www.gutenberg.org/files/205/205-0.txt> in your browser. Check it out and see for yourself.

## Viewing Data at the Command Line

Now that we've downloaded Gutenberg's edition of *Walden, and On The Duty Of Civil Disobedience* and saved it to a file, let's look inside it.

Try using `cat` to do this. You'll find it all goes by too fast to get any sense of it. (You can click <kbd>control</kbd> + <kbd>c</kbd> on your keyboard to cancel the output if it's taking too long.)

Instead, let's look just at what's at the top ("head") of the file:

```console
$ head walden-gutenberg.txt
```
&hellip; and just at what's at the bottom ("tail") of the file:

```console
$ tail walden-gutenberg.txt
```
Using another command, `less`, we can get the text delivered to us a page at a time. 

```console
$ less walden-gutenberg.txt
```

To page through the file, use the following keyboard shortcuts (that should work on Windows using Git Bash or on macOS terminal):

Click the <kbd>f</kbd> key to view forward one page, or the <kbd>b</kbd> key to view back one page.

Once you're done, click the <kbd>q</kbd> key to return to the command line.

Notice that there's a lot of text at both the top and bottom of this file that's not Thoreau's. It's Gutenberg's boilerplate text about terms and conditions.

When working with data that you download from the web, it's often necessary to make adjustments to it — "clean" it — before it will be useful to you.

← [Editing from the Command Line](12-editing-from-the-command-line.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Analyzing Text Data](14-analyzing-text-data.md) →