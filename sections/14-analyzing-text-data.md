← [Exploring Text Data](13-exploring-text-data.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Review and Next Steps](15-review-and-next-steps.md) →

---

# 14. Analyzing Text Data

Let's do some very basic analysis of *Walden*. The tools we'll use to do this are rough; they won't yield information as accurate as what we'd get using a programming language such as Python or R. But precision isn't our aim here; we just want to get a quick sense of some things we can do with plain text content at the command line.

## Counting

We can count the words in *Walden* by piping the text content to `wc`, just as we did in an earlier example with text we created ourselves. The command below streams the full content of the file, then turns that stream into input for the command `wc -w`, which says, "Count the words in this input."

```
$ cat walden.txt | wc -w
106286
```

We can list the words in *Walden*. The command below, `grep`, is very powerful. It stands for "global regular expression print." A regular expression is a pattern of characters. In the command below, the regular expression `\b\w+\b` matches any string containing one or more letters or numbers (`\w+`) surrounded by some kind of border (`\b`), which is most likely to be an empty space (the space separating words). We add the two flags `-E` and `-o` (which we can abbreviate as `-Eo` ) to "extend" the regular expressions grep will recognize (`-E`) and extract the matches from the file (`-o`), putting each match on its own line.

```
$ grep -Eo '\b\w+\b' walden.txt
```
Scroll up and down in the output from this command, and you'll quickly recognize that you're looking at *Walden* from the first word to the last, one word per line.

We can repeat this command (use the <kbd>up arrow</kbd>) and add a pipe to the end of it to count the number of lines we get when we put one word on a line.

```
$ grep -Eo '\b\w+\b' walden.txt | wc -l
107714
```
This is a different result from the one we got using `cat` and `wc -w`. Why? This approach counts not only strings of letters but strings of digits, so it also captures dates and other numbers in *Walden*. Whether we want to include those in our word count will depend on what we're trying to accomplish in our analysis.

What if we want to list all the words in *Walden* in alphabetical order? We can extract our bordered character-strings (letters or numbers), then pipe them to the `sort` command. The `-f` flag will cause the sort to ignore whether the extracted words begin with an uppercase or lowercase letter, so that "zig" and "Zilpha" are listed together. Otherwise all the words beginning with uppercase letters would be listed, A-Z, before all the words beginning with lowercase letters.

```
$ grep -Eo '\b\w+\b' walden.txt | sort -f
```

If you scroll through this list, you'll notice that every instance of "a" or "the" is listed on its own line. These are *all* the words of *Walden*, simply rearranged into an alphabetical list.

It might be more useful to have a list of all the *unique* words in *Walden*, so that no single word is listed more than once. We can do that by adding the `-u` flag to `sort`, thus:

```
$ grep -Eo '\b\w+\b' walden.txt | sort -uf
```
If we want to save this list to a file so we can come back to it, we can do that with a redirect:

```
$ grep -Eo '\b\w+\b' walden.txt | sort -uf > walden_unique_words.txt
```
How many unique words are there in *Walden*? 

```
$ grep -Eo '\b\w+\b' walden.txt | sort -uf | wc -l
10707
```
Now that we have a total word count for *Walden*, we can do a little math. The ratio of unique words to total words in a text is sometimes used as a measure of the text's "lexical richness" or "lexical diversity." For *Walden*, this figure would be 10707/107714 or 0.09940212043002766. If that seems like a small number, consider that most texts recycle a lot of words, especially words like "a" and "the."

## Searching

The `grep` command is a search tool. We can use it not only to count, but also to locate strings of characters in a text.

To find all the instances of the string `water` in *Walden*, we could type:

```
$ grep -En --color=always 'water' walden.txt
```
In place of `-Eo`, we've used `-En` here. For this search, we didn't want to "extract" the strings we found; instead, we wanted to see them in context. The `-n` flag tells the shell to print line numbers to the left of the lines, which might be helpful for locating a particular result. The `--color=always` option ensures that the search string is highlighted in a different color, making it easier to see.

If you scroll through your search results, you'll notice that your search picked out not only instances of the word "water" but also related words such as "watery" and "waters." If you wanted to exclude such words, you could use the `\b` delimeter in your regular expression, as we did earlier:

```
$ grep -En --color=always '\bwater\b' walden.txt
```
## Obtaining texts and other data from the web

For this tutorial, you were provided with a file containing the text of *Walden*. You obtained the file by clicking a link to download it to your computer.

You can also download texts and other data directly from the command line. One way to do this is to use `curl`. "Curl," sometimes written "cURL," is an acronym for "client URL." If you point `curl` at a file located at a URL on the web, `curl` will stream the content of that file to your shell, where it can be printed to your screen, piped as input to another command, or written to a file that you can save to disk. To obtain your own copy of *Walden,and On the Duty of Civil Disobedience* from [Gutenberg.org](https://www.gutenberg.org/), you could type this:

```
$ curl https://www.gutenberg.org/files/205/205-0.txt
```

To save it to a file, so that you can open it in VS Code or another plain-text editor, you could type:

```
$ curl https://www.gutenberg.org/files/205/205-0.txt > walden-gutenberg.txt
```

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

Notice that the links on this page, if they function at all, will take you back to the 

The page looks pretty much as it does on the web, you don't have to be connected to the web to read it.

On pages that contain minimal styling and few or no images, what you see offline will differ very little from what you see online. For example, compare how Neal Stephenson's essay, ["In the Beginning ... Was the Command Line"](http://cristal.inria.fr/~weis/info/commandline.html) looks on the web to what you see if you `curl` the page, save it to a file (remember to give it the `.html` extension!) and display the saved page in your browser while offline.

## Learn more about grep and regex

If you want to get a little more milage out of the grep command, refer to [this tutorial on grep and regular expressions](https://www.digitalocean.com/community/tutorials/using-grep-regular-expressions-to-search-for-text-patterns-in-linux). Regular expressions (or regex) provide methods to search for text in more advanced ways, including specific wildcards, matching ranges of characters such as letters and numbers, and detecting features such as the beginning and end of lines. If you want to experiment with regular expressions in an easy-to-use environment, numerous regex test interfaces are available from [a simple google search](https://www.google.com/search?w&q=regex+tester), such as [RegExr](https://regexr.com/), which includes a handy cheat sheet.

## Evaluation

Let's think about the `grep` command.

- It searches the given file for lines containing a match to the given strings or words.*
- It can be combined with other commands, so as to produce a search that matches their output.*
- It produces a new file with the lines containing the strings or words you are searching.
- It delete the strings or words you are searching from a file.

---

← [Exploring Text Data](13-exploring-text-data.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Review and Next Steps](15-review-and-next-steps.md) →