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

1. ###### `git rebase <nameOfBranch>`
![Git rebase example](https://wac-cdn.atlassian.com/dam/jcr:4e576671-1b7f-43db-afb5-cf8db8df8e4a/01%20What%20is%20git%20rebase.svg?cdnVersion=486)
> Rebasing is the process of moving or combining a sequence of commits to a new base commit. It's useful alternative to merging because it gives a cleaner repo history which can help us troubleshoot bugs faster.
- **Don't rebase in public branches! The rebase would replace the old commits with new ones and it would look like that part of your project history abruptly vanished.**
- `git log -3` //to see most recent commits (to be exact, last 3 on this example).
- [Git Rebase clean explanation!](https://www.youtube.com/watch?v=_UZEXUrj-Ds)

#
2. ###### `git merge`
> In the most frequent use cases, git merge is used to combine two branches. When creating a merge commit Git will attempt to auto magically merge the separate histories for us. If Git encounters a piece of data that is changed in both histories it will be unable to automatically combine them. That's why we should be prepared for merge:
- Confirm the receiving branch -> Execute git status to ensure that HEAD is pointing to the correct merge-receiving branch. If needed, execute git checkout to switch to the receiving branch. 
- Fetch latest remote commits -> Make sure the receiving branch and the merging branch are up-to-date with the latest remote changes. Execute git fetch to pull the latest remote commits. Once the fetch is completed ensure the main branch has the latest updates by executing git pull.
- Execute `git merge <.>` where <.> is the name of the branch that will be merged into the receiving branch.
[Git merge example](https://wac-cdn.atlassian.com/dam/jcr:c6db91c1-1343-4d45-8c93-bdba910b9506/02%20Branch-1%20kopiera.png?cdnVersion=486)

#
3. ###### `git pull`
 
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
  
  
  
---
## Terminal 
  1. basic commands like mkdir, cd, echo, cat, ls, grep
  1. vim - create, edit file
  1. ssh
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


  
