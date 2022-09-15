
# Git and Github

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