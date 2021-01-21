![Header image for the Command Line workshop](https://raw.githubusercontent.com/DHRI-Curriculum/command-line/v2.0/_django-meta/header%403x.png)

This fall 2020 workshop at SUNY Geneseo re-uses [content](https://github.com/DHRI-Curriculum/command-line) shared openly by the [Digital Humanities Research Institute](https://www.dhinstitutes.org/) at the CUNY Graduate Center. A few modifications have been made to tailor the content to our Geneseo community.

To prepare for the workshop, you should 

1. **All users:** [Follow these instructions](https://github.com/DHRI-Curriculum/install/blob/v2.0/guides/visual-studio-code.md) to download and install Microsoft's free text-editor, Visual Studio Code. (Be sure to complete all the configuration steps in the instructions.)
2. **Windows users only:** [Follow these instructions](https://github.com/DHRI-Curriculum/install/blob/v2.0/guides/git.md#installation-instructions-microsoft-windows-10) to download and install Git and Git Bash. Git Bash will enable you to issue commands on your Windows machine the same way you would in MacOS or Linux. 

## What this workshop is about

Most of us interact with our computers by clicking on icons of files and folders, choosing actions from dropdown menus, and working with our scholarly, creative, or personal content inside little windows whose appearance and functionality are designed by companies such as Apple, Microsoft, Google, and Adobe. 

This *graphical user interface* (GUI, or "gooey," for short) greatly simplifies many computing tasks and empowers us in many ways.

But it also obscures from us what our computers are actually *doing* when we use them. And when we rely entirely on the GUI, we're allowing a small number of (mostly) proprietary companies to mediate our computing experience.

Learning to use your computer's command line can increase your freedom and autonomy as a scholar, creator, and citizen. It can also enable you to do some pretty cool things.

## What we'll cover

This workshop is a very basic introduction to the command line, designed to get you started down the road to greater power and agency. As we move through it, you'll  

- Learn common commands to create files (`touch` and `echo`)
- Learn commands to create directories (`mkdir`)
- Navigate your file structure using change directory (`cd`), print working directory (`pwd`), and list (`ls`)
- Move content from one place to another using redirects (`>`) and pipes (`|`)
- Explore textual content in a literary work using word and line counts, `head` and `tail`, and the concatenate command `cat`
- Search textual content using the `grep` command
- Create and sort cheat sheets for the commands we learn

---

<p align="center">This workshop is estimated to take you 3 hours to complete.</p><p align="center"><a href="sections/01-what-is-the-command-line.md">Get Started</a> →</p>

---

## Lessons

### Part one

1. [What Is the Command Line?](sections/01-what-is-the-command-line.md)
2. [Text Editors](sections/02-text-editors.md)
3. [Why is the Command Line Useful?](sections/03-why-is-the-command-line-useful.md)
4. [Getting to the Command Line](sections/04-getting-to-the-command-line.md)
5. [Prefatory Pro Tips](sections/05-prefatory-pro-tips.md)
6. [Navigation](sections/06-navigation.md)
7. [Creating Files and Folders](sections/07-creating-files-and-folders.md)
8. [Creating a Cheat Sheet](sections/08-creating-a-cheat-sheet.md)
9. [Pipes](sections/09-pipes.md)
10. [Interlude](sections/10-interlude.md)

### Part two

11. [Removing Files and Folders](sections/11-removing-files-and-folders.md)
12. [Editing from the Command Line](sections/12-editing-from-the-command-line.md)
13. [Exploring Text Data](sections/13-exploring-text-data.md)
14. [Analyzing Text Data](sections/14-analyzing-text-data.md)
15. [Review and Next Steps](sections/15-review-and-next-steps.md)

---

## Before you get started

Reminder: to complete the workshop, you'll need:

- A plain text editor. We recommend [Visual Studio Code](https://github.com/DHRI-Curriculum/install/blob/v2.0/guides/visual-studio-code.md). It isn't superior to all other text editors, but you'll probably find it easier to follow along if you're using the same editor as the workshop leaders.
- To know what operating system you're using. If you are on a Mac, you will be using an application included on all Macs called Terminal. If you're using Windows, you will need to install Git Bash, following [these instructions](https://github.com/DHRI-Curriculum/install/blob/v2.0/guides/git.md#installation-instructions-microsoft-windows-10), so that we can work in the cross-platform Unix command line for this session.

### Ethical Considerations

Before you start the Introduction to the Command Line workshop, we want to remind you of some ethical considerations to take into account when you read through the lessons of this workshop:

- "The command line" is laden with masculine and military metaphors, which is reflective of the history of computing and programming. As Wendy Hui Kyong Chun discusses in ["On Software, or the Persistence of Visual Knowledge" (2004)](https://doi.org/10.1162/1526381043320741), almost all computers (as in human computers) in the US during World War II were young women. Human computers received commands from analysts&mdash;predominantly men with the military&mdash;that they then had to interpret and act upon the machine. As Chun (p. 34) argues

    > computation depends on 'yes, sir' in response to short declarative sentences and imperatives that are in essence commands ... The command line is a mere operating system (OS) simulation.

  If commands are the ways in which a user communicates with machines, the command line (of computers today) receives these commands as text that is typed in.

### Pre-reading suggestions

Before you start the Introduction to the Command Line workshop, you may want to read a couple of our pre-reading suggestions:

- [Neal Stephenson's "In the Beginning... Was the Command Line"](http://cristal.inria.fr/~weis/info/commandline.html) is a useful piece to grasp the relationship between (and the affordances of) the command line and the GUI.
- [Douglas Rushkoff's *Program or Be Programmed*](https://rushkoff.com/books/program-or-be-programmed/) offers some reflections on how using the command line allows one to communicate in a less mediated way with their machines and the importance of doing so in the current technoscape.

### Projects that use these skills

You may also want to check out a couple of projects that use the skills discussed in this workshop:

Mastering the command line will prove useful in a great number of projects.

- Most Python- and R-based projects will require you to have some knowledge of the command line. At a very basic level, you will be invoking a Python script and will be using values of command line arguments when creating and running your scripts.
- The command line is also useful for setting up installations of server side software like [Omeka](www.omeka.org). The command line will allow you to navigate the file structure of your server. Commands like ls, mkdir, rmdir, cd, etc. are really important. For example, grep could help you find a plugin directory that you might have accidentally placed in the wrong location.
- A recent digital capstone project by Christofer Gass runs a Python script on the [command line](https://academicworks.cuny.edu/gc_etds/3786/)
- [Awesome Bash](https://github.com/awesome-lists/awesome-bash), "a curated list of delightful Bash scripts and resources."

---

<p align="center"><a href="sections/01-what-is-the-command-line.md">Get Started</a> →</p>

---

## Acknowledgements

This workshop is the result of a collaborative effort of a team of people, mostly involved presently or in the past, with the Graduate Center's Digital Initiatives. If you want to see statistics for contributions to this workshop, you can do so [here](https://www.github.com/DHRI-Curriculum/command-line/graphs/contributors). This is a list of all the contributors:

- Current Author: [Stefano Morello](https://github.com/smorello87)
- Past contributing Author: [Kelsey Chatlosh](https://github.com/kchatlosh)
- Past contributing Author: [Patrick Smyth](https://github.com/smythp)
- Past contributing Author: [Mary Catherine McKinniburgh](https://github.com/mckinniburgh)
- Past contributing Author: [Jojo Karlin](https://github.com/jojokarlin/)
- Past reviewer: [Di Yoong](https://github.com/dyoong)
- Current editor: [Lisa Rhody](https://github.com/lmrhody)
- Current editor: [Kalle Westerling](https://github.com/kallewesterling)

---

<sub>[Digital Research Institute (DRI) Curriculum](http://purl.org/dc/terms/) by [Graduate Center Digital Initiatives](https://gcdi.commons.gc.cuny.edu/) is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/). Based on a work at <https://github.com/DHRI-Curriculum>. When sharing this material or derivative works, preserve this paragraph, changing only the title of the derivative work, or provide comparable attribution.</sub>

[![Creative Commons License](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-sa/4.0/)
