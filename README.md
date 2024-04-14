# GitGud

## Index

  - [Necessary Git commands](#necessary-git-commands)
  - [Getting started with GitHub](#getting-started-with-github)
    - [Create a GitHub account](#create-a-github-account)
    - [How to install Git](#how-to-install-git)
    - [How to setup remote access on GitHub](#how-to-setup-remote-access-on-github)
  - [Making your first commit](#making-your-first-commit)
    - [How to make a GitHub repository](#how-to-make-a-github-repository)
    - [Begin working on the repository](#begin-working-on-the-repository)
  - [Making your first open-source contribution](#making-your-first-open-source-contribution)
  - [Merge and Rebase](#merge-and-rebase)
    - [Git Merge](#git-merge)
    - [Git Rebase](#git-rebase)
  - [FAQs](#faqs)
    - [What if I made changes that I don't want to commit?](#what-if-i-made-changes-that-i-dont-want-to-commit)
    - [What if I accidentally made a commit?](#what-if-i-accidentally-made-a-commit)
    - [What if I already have code written?](#what-if-i-already-have-code-written)
    - [How do I revert changes back to a specific commit?](#how-do-i-revert-changes-back-to-a-specific-commit)
    - [What's the difference between `git pull` and `git fetch`?](#whats-the-difference-between-git-pull-and-git-fetch)
    - [How do I create a new branch?](#how-do-i-create-a-new-branch)
    - [What's the difference between `git merge` and `git rebase`?](#whats-the-difference-between-git-merge-and-git-rebase)
    - [I am getting an error that isn't listed here](#i-am-getting-an-error-that-isnt-listed-here)
  - [What we learnt](#what-we-learnt)

## Necessary git commands

| Command                  | Description                                                                                                                              | Example                                                          |
| :----------------------- | :--------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------- |
| init                     | initializes a new git repository in current directory                                                                                    | `git init`                                                      |
| clone \[repo url\]       | create a local copy (clone) of an existing repository                                                                                    | `git clone https://github.com/<username>/<repository-name>.git` |
| add \[file(s) \| <.>\]   | adds file changes to the staging area so that they can be committed                                                                      | `git add file1 file2 folder`                                    |
| commit -m \<message\>    | records changes to the repository, creating a new commit with a descriptive message                                                      | `git commit -m "Placeholder message"`                           |
| status                   | displays the current state of the repository, including changes that have been staged or not staged for commit, untracked files and more | `git status`                                                    |
| log                      | displays a chronological list of commits in the repository, showing commit hashes, authors, dates, and commit messages                   | `git log`                                                       |
| branch                   | creates a new branch with the specified name. branches allow for parallel development and isolation of features or fixes                 | `git branch <branch-name>`                                      |
| checkout \<branch-name\> | switches to a different branch or a specific commit, updating the working directory to match the state of the chosen branch or commit    | `git checkout <branch-name>`                                    |
| pull                     | fetches changes from the remote repository and merges them into the current branch                                                       | `git pull`                                                      |
| push                     | uploads local changes to the remote repository, making them accessible to others                                                         | `git push`                                                      |

## Getting started with GitHub

### Create a GitHub account

**What is "GitHub"?**

GitHub is a web-based platform built around Git, a distributed version control system.
It provides hosting for software development projects using Git repositories and offers a wide
range of features aimed towards collaboration, code review, and project management.

Go to [GitHub](https://github.com) and sign up to create a new account if you don't already have one.

### How to install git

**What is "Git?"**

Git is a version control system made to track changes during development of a software based project.
It is used by developers to manage collaboration, different versions of files and much more.

**Linux**

Use your respective package managers to install git, for example on Debian based systems
`sudo apt install git-all`

**Windows**

1. Download the installer -> [.exe link](https://git-scm.com/download/win)
2. Follow the installation wizard (GUI)
3. Set your username and email
   - username: `git config --global user.username <username>`
   - email: `git config --global user.email <email>`

_NOTE: Do not change any preset installation setting in the wizard (unless you know what you are doing)_

[Reference Link](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### How to setup remote access on GitHub

There are two ways of setting up remote access privilege on GitHub HTTP and SSH, but in this session we will be focusing on only one of them, i.e., HTTP

**HTTPS**

1. Create a Public Access Key
2. If you are on Linux, heres how you use credentials for GitHub `git config --global credential.helper 'cache --timeout=31536000'`
3. If you are on Windows, use `git config --global credential.helper manager` and then you should get pop ups for credentials
4. Go to the Settings page (click on user icon on top right then settings)
5. Scroll down till you see developer settings and click on it
6. Go to Personal Access Tokens, then tokens classic
7. Generate a new token, then click classic
8. Give it necessary permissions
9. Copy access token
10. Pull a repo using http, then paste access token when prompted for a password

_NOTE: The access token is only visible once and when the tab is closed its not viewable again so don't forget to save it_

## Making your first commit

For this example we will be creating your own personalized `README.md` file which gets displayed whenever someone views your page.

### How to make a GitHub repository

**What is a "repository"?**

So has everyone use google drive to store things before? Good, a repository is like Google Drive but for code.
It is a cloud storage space where typically software projects are stored and managed for hosting and collaboration purposes.
Basically it is one big folder filled with code files necessary to make a project work out of the box, so that it becomes easy to share projects with others.

**Steps to create one**

1. Go to your repositories tab -> `https://github.com/<username>?tab=repositories` and click on `New`
2. Name your repository your username, i.e. for example my repository is called `Aditya-Jyoti` which is my `<username>`
3. Give it a description (optional)
4. Make it Public
5. Click on `Add a README file`
6. Select a license (pick MIT)
7. Click on `Create Repository`

### Begin working on the repository

1. Clone the repository `git clone https://<username>//<username>.git`
2. Open the repository and the README.md in your favorite text editor
3. Make changes, for example, add a description of yourself
4. Add the file to staging `git add README.md`
5. Add a descriptive commit message `git commit -m "Update readme"`
6. Push the repository to github `git push`

```bash
git remote add origin <url>
```

6. Add, Commit and Push your changes

Now you can use your repo normally like you would anytime else.

## Making your first open source contribution

Head on over to your first open source project called [Introduce Yourself](https://github.com/Aditya-Jyoti/Introduce-Yourself/) and read its [CONTRIBUTING.md](https://github.com/Aditya-Jyoti/Introduce-Yourself/blob/main/CONTRIBUTING.md) file. It should have all instructions provided and should get you started with contributing to that project.

## Merge and Rebase

Pray to god that you don't have to come to this, but now that you have here's what merge hell is.

### Git Merge

<p align="center">
<img src="/assets/git-merge.png">
</p>

Think of merging like stacking your new Lego pieces on top of your existing structure.
You keep both the original bricks and the new ones, creating a taller tower.
This is like when you have your main project (let's say a castle), and you want to add a tower (new feature) to it.
You just put the tower on top, and now your castle has a new addition.

**How to git merge?**

1. First move to the branch you want to merge changes into

```bash
git checkout <branch-name>
```

2. Now it is a good practice to fetch your changes

```bash
git fetch
```

The main difference between `git pull` and `git fetch` is that git pull auto merges for you,
hence it may and may not work during merging.

3. Now merge the branch onto your current branch

```bash
git merge <merging branch>
```

4. Resolve conflicts

- Go to your code and you'll see some arrow `>>>` or `<<<` and equals `===`
- `>>>` means the start of the change
- `<<<` means the end of the change
- Everything on top of the `===` is the content from current branch and everything below is the content from branch being merged.
- delete arrows and equals as you go keeping or removing stuff as you go

5. Add, Commit and Push your changes

### Git Rebase

<p align="center">
<img src="/assets/git-rebase.png" />
</p>

It's like taking your tower apart and rebuilding it with the new pieces added in between.
So, instead of stacking the new pieces on top, you sort them out and insert them into your original tower one by one.
This way, everything stays in order. This is similar to realizing you built your tower (branch)
in the wrong spot, so you take it apart and rebuild it in the right place with
the new pieces added in where they fit better.

**How to git rebase**

1. Set rebase to true

```bash
git config pull.rebase true
```

2. Git pull

- Now you should see a bunch of warnings and it should pop you into rebase mode
- Use `git rebase --continue` to move on to the next commit, if its the end of the rebasing commits then it moves to main
- Use `git rebase --abort` to get back to the state before you ran `git rebase`
- Just like merge go on and keep/remove changes that you want/don't want and keep adding and committing then

3. Once done `git push`

## FAQs

### What if I made changes that I don't want to commit?

Here we use the `git stash` command to temporarily store changes in your working directory without committing them

1. stash you changes `git stash`
2. apply your changes `git stash apply`

**extra**

- `git stash list`: check your stashed changes
- `git stash apply stash@{number}`: apply a specific stash
- `git stash pop`: apply stashed changes and remove it from the list
- `git stash clear`: remove all stashed changes

### What if I accidentally made a commit?

So you made some changes that you accidentally committed? Here we can revert to last commit and stash new changes to get a new working space

1. run `git reset HEAD^` to undo the last commit
2. run `git stash` to stash your changes

Now you should be back to where you were without having committed.

_NOTE: only stash if you don't want to use the changes that you just made_

### What if I already have code written?

There are times when you have already written down some code so cloning a repo then adding your changes becomes a pain. Thats where `git init` command shines.

Here's how you initialize a git repo locally and then add it globally to github.

1. Go to any folder which you want to make a git repo of
2. Type in `git init .` this should make the current folder a git repo (adds a .git folder)
3. Now go to GitHub and create a blank repo
4. Copy its clone link (http/ssh)
5. Come over to where you initialized a new repo and add a new remote

### How do I revert changes back to a specific commit?

If you want to go back to a specific point in your project's history, you can use the `git checkout` command followed by the commit hash you want to revert to.

1. Find the hash of the commit you want to revert to by using `git log`.
2. Run `git checkout <commit-hash>` to revert your project's state to that specific commit.

### What's the difference between `git pull` and `git fetch`?

`git pull` and `git fetch` are both used to update your local repository with changes from a remote repository, but they work slightly differently.

- `git pull`: This command fetches changes from the remote repository and merges them into your current branch. It's essentially a combination of `git fetch` and `git merge`.
- `git fetch`: This command only fetches changes from the remote repository and stores them in your local repository. It doesn't automatically merge them into your current branch. You'll need to use `git merge` or `git rebase` to incorporate the fetched changes into your branch.

### How do I create a new branch?

Creating a new branch allows you to work on new features or bug fixes without affecting the main codebase. Here's how you can create a new branch:

1. Run `git checkout -b <branch-name>` to create a new branch and switch to it in one step.
2. Make your changes on the new branch.
3. When you're ready to merge your changes into the main branch, you can use `git merge` or create a pull request on GitHub.

### What's the difference between `git merge` and `git rebase`?

Both `git merge` and `git rebase` are used to integrate changes from one branch into another, but they do it in different ways.

- `git merge`: This command integrates changes by merging the commits from one branch into another. It creates a new commit to record the merge, preserving the commit history of both branches.
- `git rebase`: This command rewrites the commit history by moving the changes from one branch onto another branch. It creates new commits for each commit in the original branch, resulting in a linear history.

Choosing between `git merge` and `git rebase` depends on your workflow and preferences.

### I am getting an error that isn't listed here

Google is your best friend. Google what error you are getting and there will almost always be someone who has faced the issue you are facing before hand.
If google doesn't help then turn to your favorite LLM for help like ChatGPT or Phind.
You could even open up an `issue` in this repository and I will reply back when I get time.

## What we learnt

So we learnt

1. What is Git?
2. What is GitHub?

Then we learnt how to

1. Create a GitHub repository
2. Clone, Add, Commit and Push changes to that repository
3. Contribute to open source projects

And then we stepped into the tough parts and saw what is

1. Git merge
2. Git rebase
