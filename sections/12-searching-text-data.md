← [Interlude](11-interlude.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[What We Have Learned](13-what-we-have-learned.md) →

---

# 12. Analyzing Text Data

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
Now that we have a total word count for *Walden*, we can do a little math:

```
$ echo $(( 10707.0/107714 * 100 ))
9.9402120430027665
```
The unique words of *Walden* represent a little under 10% of the total word count. That may seem like a small proportion, but it's not an unusual one, even in a highly literary text like *Walden*. Most texts recycle a lot of words, especially words like "a" and "the."

This proportion is sometimes said to indicate the "lexical richness" or "lexical diversity" of a text.

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

## Bonus

If you want to get a little more milage out of the grep command, refer to [this tutorial on grep and regular expressions](https://www.digitalocean.com/community/tutorials/using-grep-regular-expressions-to-search-for-text-patterns-in-linux). Regular expressions (or regex) provide methods to search for text in more advanced ways, including specific wildcards, matching ranges of characters such as letters and numbers, and detecting features such as the beginning and end of lines. If you want to experiment with regular expressions in an easy-to-use environment, numerous regex test interfaces are available from [a simple google search](https://www.google.com/search?w&q=regex+tester), such as [RegExr](https://regexr.com/), which includes a handy cheat sheet.

## Evaluation

Let's think about the `grep` command.

- It searches the given file for lines containing a match to the given strings or words.*
- It can be combined with other commands, so as to produce a search that matches their output.*
- It produces a new file with the lines containing the strings or words you are searching.
- It delete the strings or words you are searching from a file.

---

← [Interlude](11-interlude.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[What We Have Learned](13-what-we-have-learned.md) →