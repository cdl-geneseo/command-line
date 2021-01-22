← [Analyzing Text Data](14-analyzing-text-data.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Start](../README.md) ↺

---

# 15. Review and Next Steps

## What we did

In this session, we learned:

- how to use `touch` and `echo` to create files
- how to use `mkdir` to create folders
- how to navigate our file structure by `cd`(change directory), `pwd` (print working directory), and `ls` (list)
- how to use redirects (`>`) and pipes (`|`) to create a pipeline
- how to remove files and folders using `rm` (remove) and `rm -r` (remove recursively)
- how to do some basic file editing from the command line using the programs Vim and Nano
- how to download content from the web to your machine using `curl`
- how to explore text files using word and line counts, `head` and `tail`, and the concatenate command `cat`
- how to search in text files using the `grep` command

And we made a cheat sheet for reference.

When we started, we reviewed what text is — whether plain or enriched. We learned that text editors that don't fix formatting of font, color, and size, do allow for more flexible manipulation and multi-program use. If text is allowed to be a string of characters (and not specific characters chosen for their compliance with a designer's intention), that text can be fed through programs and altered with automated regularity. Text editors are different software than Bash (or Terminal), which is a text-based shell that allows you to interact directly with your operating system giving direct input and receiving output.

## A few other things you should know

### Getting help from the web

If you get stuck at the command line or just can't remember how to use a particular command, you can often get good help quickly by typing a few key words into your favorite search engine. We'd say "Just Google it" if it weren't for the fact that we'd rather not reinforce the belief that Google is the only good search engine out there. (Actually, we're fans of [DuckDuckGo](https://duckduckgo.com), since its business model doesn't rely on monetizing your personal information.) Anyway, the important point is just that you'll find many websites out there that explain basic command-line concepts and offer solutions to particular problems. Just remember to consider the usual markers of reliability when looking at the blogs and websites of individual developers. One nice thing about a community website, such as [stackoverflow](https://stackoverflow.com/questions), is that you can easily see how the community has evaluated suggestions and solutions posted there.

### Getting help at the command line

An easy way to get documentation on many commands is to use the command line itself. At the command prompt, type `man`, followed by the name of a command, for that command's "manual," or try typing the name of the command followed by `--help`. You can then page through the output using your keyboard's arrow keys, space bar, or, if you have them, "page up" and "page down" keys. Type `q` to return to the terminal prompt. 

Examples:

```console
$ man cd
$ grep --help
```
### Exercise special care with these three commands

Here are three commands that you should handle with particular care.

- `sudo`
- `rm`
- `mv`

Be especially careful with `sudo`, which is typed in front of any command that you want to execute as a "superuser" — that is, as your computer's administrator. If you turn to the web for an answer to a command-line question, we recommend that you stay away from any solution that involves `sudo` unless you're absolutely certain you know what you're doing. Why? When you're making changes to your computer as administrator, you're altering files and file structures that are responsible for the computer's basic functioning. Mistakes here can have very serious consequences.

The `rm` command is used to delete ("remove") files and folders. It's powerful and extremely useful, but you need to keep in mind that when you delete content from your computer with `rm`, the content doesn't go to your Trash folder; it goes straight out the door. It's gone.

The `mv` command is highly useful for moving files and folders from one location to another. Technically, what you're doing is *renaming* the file or folder. (If you stop to think about it, a file's full name is just its location in your file hierarchy: e.g., `/Users/schacht/Documents/myfile.txt`. Its new name is therefore a new path, putting it effectively at a new location, which may or may not be in the same directory. This is perhaps easiest to wrap your head around if you think of a file's `name/path` as an address, like a postal address. That address is where you can "reach it" to read its contents or do something else with it.) 

If you don't use `mv` properly, though, you can end up accidentally overwriting existing file content. This isn't a reason not to use it, just a reason to think before you type.

Which leads to our next tip &hellip;

### Back up!

Okay, this isn't specifically a command-line tip, but we're doing you a big favor by reminding you that backing up your computer should be as much a part of your daily routine as brushing your teeth. There are a variety of options for backing up your data. CIT has a [self-help guide](https://wiki.geneseo.edu/x/0AGXBQ) that will walk  you through them.

If you regularly back up your computer, you'll breathe a lot easier at the command line because you'll know you have a way to recover any data that you accidentally delete.

### Exit gracefully

When you're done with a session in your shell, you can exit the shell by typing `exit` at the command prompt. To start a new session, you can simply open a new window or tab in your terminal application (Terminal on the Mac, Git Bash in Windows).

Remember, as well, the two common commands we discussed in the workshop for getting back to the command prompt. One is `q` (used, for example, to stop viewing a file's content). The other is <kb>ctrl-C</kb> (often used to interrupt a process that you want to abandon because it's taking too long to run or wasn't what you wanted to run in the first place.)

## Some next steps you might want to take

*&hellip; not necessarily in this order:*

- Explore the resources at [Awesome Bash](https://github.com/awesome-lists/awesome-bash).
- Learn how to spiff up your command-line interface and add new capabilities to your shell by moving from bash to zsh and installing [oh-my-zsh](https://ohmyz.sh/).
- Explore Geneseo's LinkedIn Learning videos (via myGeneseo) on the terminal, the command-line, shell scripting, programming languages, and web development.
- Learn how to use [regular expressions](http://www.rexegg.com/) (aka "regex") in your command-line searches and inside the wide range of software applications that support it, then sharpen your regex skills or test your expressions using the interactive [regexr](https://regexr.com/). 
- Learn how to install additional programs that you can use on the command-line using a package manager such as [Homebrew](https://brew.sh/) (for MacOS) or Apt (for Linux).
- Learn about Git (a versioning tool that was used to build this website and is most powerful when used from the command line) and GitHub (the cloud service that hosts this .website and that open-source developers use to collaborate on all sorts of projects, especially software).
- Learn to write plain text documents in [Markdown](https://en.wikipedia.org/wiki/Markdown), a simple syntax that's easily converted to a range of other formats, such as HTML or PDF and that's incredibly useful for, among other things, lightweight, portable note-taking.
- Learn about [pandoc](https://pandoc.org/), a super-useful command-line tool for converting files from one format to another (for example, Markdown to .docx, .pdf, or .epub).
- If you're a Mac person, check out the [Command Line series](https://osxdaily.com/category/command-line/) at the blog [OSXDaily](https://osxdaily.com), where new command-line tips and tricks for troubleshooting and productivity on the Mac appear regularly.
- If you're a humanist, check out [The Programming Historian](https://programminghistorian.org), which publishes "novice-friendly, peer-reviewed tutorials that help humanists learn a wide range of digital tools, techniques, and workflows to facilitate research and teaching." It's a fantastic resource. Find the site at

---

← [Analyzing Text Data](14-analyzing-text-data.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Start](../README.md) ↺