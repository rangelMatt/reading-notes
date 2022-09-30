# Code 401 Prep: Practice in the Terminal Reading Notes

## [Bash Command Line Tutorial](https://ryanstutorials.net/linuxtutorial/)

1. **[The Command Line!](https://ryanstutorials.net/linuxtutorial/commandline.php)**
   - What is it, how does it work and how do I get to one.
     - A command line is a text based interface to the system. You can enter commands by typing them on the keyboard and feedback will be given to you similarly as text.
     - For Mac:Find the program `Terminal` under **Applications -> Utilities**. Fastest way, type `command + space`, then start typing 'Terminal' and it will show up.
     - For Linux: find it in **Applications -> System** or **Applications -> Utilities.** Also you can 'right-click' on the desktop and there may be an option 'Open in terminal'.
2. **[Basic Navigation!](https://ryanstutorials.net/linuxtutorial/navigation.php)**
   - An introduction to the Linux directory system and how to get around it.
     - 'PWD(Print Working Directory)', might be a great tool to copy and paste into another terminal, for reasons.
3. **[More about Files](https://ryanstutorials.net/linuxtutorial/aboutfiles.php)**
   - Find out some interesting characteristics of files and directories in a Linux environment.
     - `Everything is a File...EVERYTHING`
     - Spaces can be confusing for file names, so be careful, as in the command line these are how we separate items.
4. **[Manual Pages](https://ryanstutorials.net/linuxtutorial/manual.php)**
   - Learn how to make the most of the Linux commands you are learning.
     - Manual pages are set of pages that explain every command available on our system including what they do. Invoke the manual pages with the following command: `man <command to look up>`
     - `man -k <search term>`, will allow one to search within a manual page. THIS WILL SAVE SO MUCH EYE STRAIN! Type '/' forward slash, followed by the term you would like to search for and hit 'enter'. Cycle through the term by pressing 'n' for next.
5. **[File Manipulation](https://ryanstutorials.net/linuxtutorial/filemanipulation.php)**
   - How to make, remove, rename, copy and move files and directories.
     - Use `mkdir [options]<Directory>` to create a directory, and make your life easier.
     - Typing `-p` after mkdir and before the file will confirm what file you are adding and removing in the terminal. Without this, the terminal doesn't confirm this.
     - `cp` Copies a file or directory.
     - `mv` Moves a file or directory as well as renaming.
     - `rm` Remove - ie. Delete a file.
6. **[Cheat Sheet](https://ryanstutorials.net/linuxtutorial/cheatsheet.php)**
   - Great resource for terminal information.

[<---BACK](README.md)
