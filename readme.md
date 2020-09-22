#### Story:
- Alice creates a local repository and then one on GitHub
- Alice adds remote the local repository to GitHub
- Alice invite Bob to this GitHub repository
- Bob clones this repository from GitHub to his local workspace
- They work local and push commits to GitHub
---
#### Alice's First Task:
I create a new folder eg. `git_exercise` and initialize as a git repository and make the first commit
1) I open VSCode and open the new folder
2) I initialize a git repository
   - 2A: I open the Source Control **Ctrl+Shift+G** and then click the Initialize repository button or
   - 2B: I open the Source Control with clicking the branch-like
     icon on the left bar and then click the Initialize repository
     button or
   - 2C:
      1. I open a terminal in VSCode
         + **Ctrl+J** on German keyboard or
         + **Ctrl+\`** on English keyboard or
         + in menu **Terminal>New Terminal**
      2. the path is now my new folder and I initialize a git repository with typing in terminal: `git init`
3) I type `git status` in terminal to check if it's ok
4) I create something eg. `readme.md` or `index.html` and save
5) I add the files to the staging area (aka. index) by typing in the terminal
   - `git add .`  or
   - `git add index.html` \
repeat #3.
6) I commit the staged files by typing `git commit -m 'initial commit'` \
repeat #3.

It is ready to push to GitHub

#### Alice's Second Task:
I create a new repository on GitHub and push the existing local one to that
1) I open GitHub in a browser and log in
2) I go to the repositories tab and click the **New** button on the right
3) I type a name without spaces eg. `test_project`   I can give a description and leave it public and then create, and don't worry about Readme .gitignore and licence
4) On the quick setup page I choose the "push an existing repository from the command line" and copy or note the first line: `git remote add origin https://github.com/olivabigyo/test_project.git`
5) I go back to the teminal and add remote the existing local repository as origin to the newly created one on GitHub
    1. I type or paste that first line: `git remote add origin https://github.com/olivabigyo/test_project.git`
    2. I don't worry about the second line: `git branch -M master`  I guess it just renames the branch to master, from 1st October the default name will be main and not master https://github.com/github/renaming
    3. I type the third line as well to actually push it:
        - `git push -u origin master` or
        - `git push --set-upstream origin master`
6) I type `git log` and `git status` to check if it's ok :)

Notes to myself: Make sure you already committed, else the push fails and the `git log` command says:
```
fatal: your current branch 'master' does not have any commits yet
```
Make sure you often repeat 6) in the future :)

#### Alice's Third Task:
I invite Bob to collaborate to this project
1) I go to the test repository on github and click on the **Settings** tab
2) I choose **Manage access** on the left menu bar
3) I click on the **Invite collaborator** button
4) I type Bob's GitHub username or Bob's email address and add Bob to the project

#### Bob's First Task
I accept the invitation and clone Alice's repository
1) I received an email from GitHub
2) I log in to GitHub else it won't work :)
3) I click the **See Invitation** link in the email
4) I click on the **Accept Invitation** button on the GitHub page 
5) On the project page I click the **Code** button and copy or note the url 
6) I open a terminal with the right path where to clone eg. `Documents/Modul_5`
   - in File Explorer right click and **GitBash here** or
   - open **GitBash** and navigate with the `cd` and `cd..` commands
6) I type `git clone https://github.com/olivabigyo/test_project.git` or 
   - I can type `git clone https://github.com/olivabigyo/test_project.git student_project` if I want to rename the project in my workspace to student_project
7) I navigate in with typing `cd test_project` or `cd student_project` if I renamed it
8) I type `git status` to check if it's ok :)

#### Bob and Alice's Workflow
I learn the `git status -s` or `git status --short` command flags in the terminal
- I can create a file eg.`style.css` then it is untracked, if I type `git status -s` or `git status --short` in the terminal then `style.css` has `??` flag
- I can modify and save an untracked file eg."make a small css reset" in the `style.css` then it is still untracked with `??` flag 
- I can add an untracked file to the staging area: `git add style.css` then it gets a simple `A ` flag
- I can modify and save a staged file eg. "make a body background-color" in the `style.css` then it has `AM` or `MM` flag as added but then modified again so it has staged and unstaged changes, if I commit now only the staged changes will be committed eg. "css reset but no background-color"
- I can modify and save an unstaged but tracked file eg. the `index.html` file is unchanged since the last clone/pull/push action, so I can "create a new div" in the `index.html` then it has ` M` flag as unstaged but modified, if I commit now, this div will be not committed

I can check these changes in the Source Control Panel in VSCode: **Staged Changes**: style.css M, **Changes**: index.html M, style.css M

So I can see that before I commit and push I have to add the index.html and the style.css again to the staging area.

Usually I work on my workspace and make changes and save and push to my GitHub repository as 
1. I add all my modified files to the staging area `git add .`
2. I commit (all staged files) with a message `git commit -m 'short description my changes'`
3. I push to origin/master on GitHub `git push` 

BUT to collaborate to the GitHub repository with Bob/Alice: 
1. I have to **pull** from GitHub to see if others made changes `git pull`
2. I have to **work and save** my changes
3. I have to **add** all my modified files to the staging area `git add .`
4. I have to **commit** (all staged files) with a message `git commit -m 'short description my changes'`
5. I have to **pull again** from GitHub when my working tree is clean to see if others already made changes `git pull`
6. I have to resolve the diffs if any
7. I have to **push** to origin/master on GitHub `git push`

Notes to myself: The `git add .` command not always the best choice, I can add unwanted or temporary files to the staging area so be careful and learn more about .gitignore, which can help.
The `git commit` without message doesn't work, always provide a description.
