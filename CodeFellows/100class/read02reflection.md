# Class 2 - The Coder's Computer

## Choosing a Text Editor

Choosing a text editor is ver important when one is coding. It doesn't matter which one, as they are all basically the same. But, find one that is best for your use. As long as the text editor you choose will help you complete a web site successfully.

## What is a Text Editor?

Some features that one should look for in a text editor are:

1. code completion
2. syntax highlighting
3. a nice variety of themes (to reduce eye strain and fatigue
4. the ability to choose from a healthy selection of extensions available when you need them

Code completion and Emmet are two valueable tools to look for in text editing. They both save time and allow you to type code faster. Code completion will give you automatic suggestions to your code as you are typing and Emmet is a type of shorthand language.

Syntax highlighting is a great feature that takes the text you type, and makes it more noticeable by colorizing the text. This allows you to look for an error much more simply.

The variety of themes help you customize background colors and font colors to your liking. Typically web developers use a dark background and brightly colored text, as this is easier on the eyes.

As you progress through your career in web developing, you will want a text editor that will grow with you. You can do this with *extensions*, which act like plugins for your text editors. This will aide you in writing code with ease.

## Text Editors are Already Available on your Computer

That's right, on Mac computers, you will come across "Text Edit". On Windows, it's "Notepad". However, on Linux computers, each distribution will come with it's own  text editor already installed depending on the distribution. Each of these come with it's own name.

When using the text editors that come on your computer, there are no extras or plugins you can use. In fact, the text editor should be bare bones. This means no buttons to make bold or italicize either.

## Third-Party Options

There are a bunch of text editor options to choose from that are changing and evolving even as we speak. It's typical to be on one for a while and then to hear about another text editor that has new and exciting features that you would want to try out. And thus, the cycle repeats when you jump from one to another throughout your career. Check out the best text editors for mac [here](https://www.techradar.com/best/best-text-editors).

## Text Editors vs. IDEs

A text editor is exactly what the title says, it edit's text. However, an IDE (Integrated Development Environment) is an array of different software in one place. It's a text editor, a file manager, a compiler, and a debugger in one software package.

-----------------

# 'The Command Line!' **Notes**

It is typical for one to have several terminals open at a time. For example, you can have a terminal open to the below at the same time:

1. currently working on
2. bring up ancilliary data
3. viewing Manual pages

A command line, or terminal, is a text based interface to the system. You can type in commands and feedback will be given to you.

### Shortcuts

When entering commands, there are stored in a history. You can revisit these past commands by using the up and down arrow keys. No need to re-type out commands, just hit the up arrow a few times. You can edit these commands using the left and right arrow keys as well.

## Basic Navigation

> Command **pwd** stands for Print Working Directory. The command does just that. It tells you what your current or present working directory is.

Use pwd when you lose track of where you are at.

> Command **ls** will show you what's in there. It stands for *list*.

> ls[options][locations]

The square brackets above reflect optional items. The terminal can be ran with or without them.

> ls -l: indicates grabbing a long listing. A long listing has the following:
>
> * First character indicates whether it is a normal ( - ) or directory ( d )
> * Next characters are permissions for the file or directory.
> * The next field is the number of blocks (don't worry to much about this).
> * The next field is the owner of the file or directory
> * The next field is the group the file or directory belongs to
> * Following this is the file size
> * Next is the file modification time
> * Finally we have the actual name of the file or directory.

> ls etc: tells ls not to list our current directory but instead to list that directories contents
> ls -l /etc: running ls with both a comman line option and argument. It shows a long listing of the directory /etc.

## Paths

> There are 2 types o fpaths we can use, **absolute** and **relative**. Wheneer we refer to a file or directory we are using one of these paths. Whenever we refer to a file or directory, we can, in fact, use either type of path (either way, the system will still be directed to the same location).

Absolute Paths specify a location in relation to the root directory, that can be identified by the forward slash(/).

Relative Paths specify a location in relation to where we currently are in the system, no slash.

> ~(tilde) - Is a shortcur for your home directory. eg:
>
> * /home/ryan/Documents is the same as typing ~/Documents
> .(dot) - This is a reference to your current directory. Written as ./Documents
> ..(dotdot)- A reference to the parent directory. Use this several times in a path to keep going up the hierarchy. eg:
> * /home/ryan is the same as typing ../../ which will do a listing of the root directory.

> ### Shortcut

> If you run the command cd without any arguments then it will always take you back to your home directory.

## More About Files

***EVERYTHING*** is a file.

Linix is Case Sensitive

Spaces in file names do not work. If there are spaces, you must use quotes *or* use escape characters.

> ### Shortcut

> In the previous section we learnt about something called Tab Completion. If you use that before encountering the space in the directory name then the terminal will automatically escape any spaces in the name for you.

You can make a hidden file by adding a . in front of the file name. There's no special command or action to make a file hidden.

When searching for the hidden file **ls** will not find it. You will need to put in **ls -a**, so that it will show hidden files and directories.

## SUM IT UP

> **file** <br> obtain information about what type of file a file or directory is.
>
> **ls -a** <br> List the contents of a directory, including hidden files.
>
> **Everything is a file under Linux** <br> Even Directories.
>
> **Linux is an extensionless system** <br> Files can have any extension they like or none at all.
>
> **Linux is case sensitive** <br> Beware of silly typos.

--------------

## Manual Pages

Manual Pages are a set o fpages that explain every command available on your system including what they do, the specifics of how you run them and what command line arguments they accept. To run it type the below:

> **man** <command to look up>
>
> To exit the man pages, press'q' for quit.

Type the below to do a keyword search on the Manual Pages

> **man -k** <search term>

## Sum it up
  
> **man** <command> <br> Look up the manual page for a particular command.
>
> **man -k** <search term> <br> Do a keyword search for all manual pages containing the given search term.
>
> **/<term>** <br> Within a manual page, perform a search for 'term'
>
> **n** <br> After performing a search within a manual page, selct the next found item.
  
Use the man pages so you can easily look stuff up.

----------------------

## File Manipulation
  
> **mkdir** <br> Make Directory - ie. Create a directory.
>
> **rmdir** <br> Remove Directory - ie. Delete a directory.
>
> **touch** <br> Create a blank file.
>
> **cp** <br> Copy - ie. Copy a file or directory.
>
> **mv** <br> Move - ie. Move a file or directory (can also be used to rename).
>
> **rm** <br> Remove - ie. Delete a file.
  
**No Undo** <br>
  The Linux command line does not have an undo feature. Perform destructive actions carefully.
  
**Command line options** <br>
  Most commands have many useful command line options. Make sure you skim the man page for new commands so you are familiar with what they can do and what is available.
  
-------------------------
  
## Vi Text Editor

> **vi** <br> Edit a file.
>
> **cat** <br> View a file.
>
> **less** <br> Convenient for viewing large files.

----------------------------------------------------
  
## Permissions

> **chmod** <br> Change permissions on a file or directory.
>
> **ls -ld** <br> View the permissions for a specific directory.
  
------------------------------------------
  
## Filters

> **head** <br> View the first n lines of data.
>
> **tail** <br> View the last n lines of data.
>
> **sort** <br> Organise the data into order.
>
> **nl** <br> Print line numbers before data.
>
> **wc** <br> Print a count of lines, words and characters.
>
> **cut** <br> Cut the data into fields and only display the specified fields.
>
> **sed** <br> Do a search and replace on the data.
>
> **uniq** <br> Remove duplicate lines
>
> **tac** <br> Print the data in reverse order.
  
**Processing** <br> Filters allow us to process and format data in interesting ways.
  
**man pages** <br> Most of the programs we looked at have command line options that allow you to modify their behaviour.
  
-----------------------------
  
> **egrep** <br> View lines of data which match a particular pattern.
  
**Regular Expressions** <br> A powerful way to identify particular pieces of information.

------------------------------
  
## Piping and Redirection
  
> **>** <br> Save output to a file.
>
> **>>** <br> Append output to a file.
>
> **<** <br> Read input from a file.
>
> **2>** <br> Redirect error messages.
>
> **|** <br> Send the output from one program as input to another program.
  
**Streams** <br> Every program you may run on the command line has 3 streeams, STDIN, STDOUT and STDERR.
  
* **STDIN** (0) - Standard input (data fed into the program)
* **STDOUT** (1) - Standard output (data printed by the program, defaults to the terminal)
* **STDERR** (2) - Standard error (for error messages, also defaults to the terminal)
  
-------------------------------

## Process Management

> **top** <br> View real-time data about processes running on the system
>
> **ps** <br> Get a listing of processes runnning on the system.
>
> **kill** <br> End the running of a process.
>
> **jobs** <br> Display a list of current jobs running in the background.
>
> **fg** <br> Move a background process into the foreground.
>
> **ctrl + z** <br> Pause the current foreground process and move it into the background.

**Control** <br> We have quite a bit of control over the running of our programs.
  
---------------------------------

## Bash Scripting
  
> **#!** <br> Shebang. Indicates which interpreter a script should be run with.
>
> **echo** <br> Print a message to the screen.
>
> **which** <br> Tells you the path to a particular program.
>
> **$** <br> Placed before a variable name when we are referring to it's value.
>
> **``** <br> Backticks. Used to save the output of a program into a variable.
>
> **date** </br> Prints the date.
>
> **if[] then else fi** <br> Perform basic conditional logic
  
**Behaves the same** <br> Anything you may do on the command line you may do in a script and it will behave exactly the same.
  
**Formatting** <br> Bash scripts are particularly picky when it comes to formatting. Make sure spaces are put where they are needed an not put when they are not needed.

[<---BACK](README.md)
  