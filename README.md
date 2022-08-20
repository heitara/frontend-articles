# frontend-articles
A repository that contains resources and useful articles for frontend developers

> The materials here are heavily inspired from `https://roadmap.sh/frontend`.

## Repository structure

[HTTP Protocol](./articles/http/README.md)


## Topics:
1. [Markdown](#markdown)
1. [Git (Github)](#user-content-git--github)
1. [Terminal](#terminal)
1. [JS](#js)
1. [NPM (NodeJS)](user-content-npm--nodejs)


## Markdown

**Markdown is a `lightweight markup language` that you can use to add formatting elements to plaintext text documents.**

**How does Markup work?**

> When you write in Markdown, the text is stored in a plaintext file that has an .md or .markdown extension. Markdown applications use something called a Markdown processor (also commonly referred to as a “parser” or an “implementation”) to take the Markdown-formatted text and output it to HTML format. At that point the document can be viewed in a web browser or combined with a style sheet and printed.

![Markdown visual representation](https://mdg.imgix.net/assets/images/markdown-flowchart.png?auto=format&fit=clip&q=40&w=1080)

[**Markdown cheat sheet**](https://www.markdownguide.org/cheat-sheet/)

---
## Git(Github)

**What's git?**

> Git is Version Control System(VCS) for traking changes in computer files. With git many people can work on the same project without having to be on the same network. 
> Usualy when we use it there is local repository that we make changes on and then we push it to a remote repository.

**Concept of Git**

- Keeps track of code history.
- Takes 'snapshots' of our files.
- We can take a 'snapshot' by making a 'commit'.
- We can visit our snapshots at any time.
#
**Imortant commands:**

1. ##### `git rebase <nameOfBranch>`
![Git rebase example](https://wac-cdn.atlassian.com/dam/jcr:4e576671-1b7f-43db-afb5-cf8db8df8e4a/01%20What%20is%20git%20rebase.svg?cdnVersion=486)
> Rebasing is the process of moving or combining a sequence of commits to a new base commit (basically rewriting history). It's useful alternative to merging because it gives a cleaner repo history which can help us troubleshoot bugs faster.
- **Don't rebase in public branches! The rebase would replace the old commits with new ones and it would look like that part of your project history abruptly vanished.**
- `git log -3` //to see most recent commits (to be exact, last 3 on this example).
- [Git Rebase clean explanation!](https://www.youtube.com/watch?v=_UZEXUrj-Ds)

#
2. ##### `git merge <nameOfBranch>`
> In the most frequent use cases, git merge is used to combine two branches. When creating a merge commit Git will attempt to auto magically merge the separate histories for us. If Git encounters a piece of data that is changed in both histories it will be unable to automatically combine them. That's why we should be prepared for merge:
- Confirm the receiving branch -> Execute git status to ensure that HEAD is pointing to the correct merge-receiving branch. If needed, execute git checkout to switch to the receiving branch. 
- Fetch latest remote commits -> Make sure the receiving branch and the merging branch are up-to-date with the latest remote changes. Execute git fetch to pull the latest remote commits. Once the fetch is completed ensure the main branch has the latest updates by executing git pull.
- Execute `git merge <.>` where <.> is the name of the branch that will be merged into the receiving branch.
![Git merge example](https://wac-cdn.atlassian.com/dam/jcr:c6db91c1-1343-4d45-8c93-bdba910b9506/02%20Branch-1%20kopiera.png?cdnVersion=486)

[Git merge vs git rebase](https://www.youtube.com/watch?v=dO9BtPDIHJ8)

#
3. ##### `git pull`
> Git pull is used to fetch and download content from a remote repo and immediately update the local repo to match that content. The biggest risk that can occur when running git pull is getting changes in a remote file that we have been working in which may cause conflics to arise in certain cases.
- `git pull <remote>` //fetch the specified remote’s copy of the current branch and immediately merge it into the local copy -> it's equal to: git fetch <remote> + git merge <current branch>
 
[Git fetch and git pull](https://www.youtube.com/watch?v=QRydepk8TB0)
 
#
**Other useful commands:**
 
- `git init` //initialize local git repository.
- `git add <file>` //add file(s) in the staging area.
- `git status` // shows what we have in the staging area and also what's ready for commit.
- `git commit`  //commit changes -> it's going to take everything that's in the staging area and put it in our local repository.
  - `git commit -m 'Changed index.html'` //it's going to commit a file with message.
- `git clone` //it's going to copy a remote repository into our current folder.
- `git rm --cached <file>` //it's going to remove a file.
- `git branch <name>` //create a branch
  - `git checkout <name>` // to switch to other branch.
- `git fetch <remote>` //fetch all of the branches from the repository -> downloads commits, files, and refs from a remote repository into our local repo (making sure that updates have occured) 
  
  
  
---
## Terminal 
  1. **Basic commands:**
   
  - `mkdir` [OPTION]... DIRECTORY... -> The command stands for "Make directory" and allows users to create directories. We can create more than one directory at a time.
    - `mkdir test` // It's going to create a folder with the name test.
    
- `cd` -> Changes directories!
    - `cd Movie` //It's going to change to Movie folder.
    - `cd ..` //Change to previous directory(parent directory).
    - `cd .` //Change to current directory.
    - `cd ~` //Change to the HOME direcory of the user that's currently logged in.
    - [How to use cd & ls](https://www.youtube.com/watch?v=5QQoKZamqpU&list=LL&index=2)
    
- `echo` [option] [string] -> The command is going to display string or variable provided by the user.
    - `echo -e` //Enables interpretation of escape charecters like: \a, \b, \c etc.
    - `echo -n` //It's going to display the content with line numbers.
   
- `cat` [option] [directory] -> The command can:
   - Display content of a file(s) -> `cat test_file.txt` or for multiple files `cat test_file1.txt test_file2.txt`
   - Redirect contents -> `cat file1.txt > file2.txt`
   - Append content from one file to another -> `cat file1.txt >> file2.txt`
   - Append text -> `cat >> file.txt`
   - Create new file -> `cat > new_file.txt`
   - [How to use `cat`](https://www.youtube.com/watch?v=nK4028I3N5U&list=LL&index=3&t=452s)
   
- `ls` [option] [directory] -> The command is used to view the content of a directory. If we want to see the content of other directories, type ls and then the directory’s path.
   - `ls -R` -> It's going to list all the files in the sub-directories.
   - `ls -a` -> It's going to show the hidden files
   - `ls -al` -> It's going to list the files and directories with detailed information like: permissions, size, owner, etc.
   - [How to use cd & ls](https://www.youtube.com/watch?v=5QQoKZamqpU&list=LL&index=2)
 
- `grep` or Global Regular Expression Print -> The command it's going to search through a file or files for a regular expression(regex) and then print out the lines where that regex was found.
   - `grep 'orage' grocery_list.txt` //It's going to search for orange in the .txt file -> oranges-yes, Orange Juice-no
   - `grep -i 'orange' grocery_list.txt` // -i it's going to ignore upper or lower-cased latters -> oranges-yes, Orange Juice-yes
   - `grep -w 'orange'.... ` // It's going to return only the lines where our regex is a single word -> oranges-no, orange juice-yes
   - `grep -c .... ` // -c It's going to return how many times our regex was found (stands for count)
  
  #
2. **vim**
 
- create
 

### Edit file:
- Switching modes:
  - `i` for insert mode.
  - `esc` for command mode.

- Navigation:
 - `k` for going up.
 - `j` for goimg down.
 - `h` for going left.
 - `l` for going right.
 
- Editing in a line:
 - `Shift + i` -> Switch to insert mode and move to the start of the line.
 - `a` -> Switch to insert mode and move to the right.
 - `Shift + a` -> Switch to insert mode and move to the end of the line.
 - `i` -> Switch to insert mode and move to the left.
 
- Making changes while in command mode:
 - `x` -> Delete the character that we are currently on.
 - `r` -> Replace the character that we are currently on.
 
#
3. ssh
---
## JS
  1. Object.* [hint](https://github.com/LeCoupa/awesome-cheatsheets/blob/master/languages/javascript.js)
  1. Inheritance (class, ES6)
  1. await/async
  1. Promises - how to create a promise, how to separete errors.
  1. bind(), call(), apply() [hint](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind)
  1. DOM - basics, events, window, document
---
## NPM & NodeJS
  1. how to setup project
  1. how to add scripts
---


  
