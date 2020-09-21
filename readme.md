Story:
Alice creates a local repository and then one on gitHub
Alice adds remote the local repository to gitHub
Alice invite Bob to this gitHub repositoryBob clones this repository from gitHub to his local workspace
They work local and push commits to gitHub

Alice's First task:
I create a new folder eg.git_exercise and initialize as a git repository and make the first commit
1) I open VSCode and open the new folder
2) I initialize a git repository
    option 2A: I open the Source Control ctrl+shift+G and then click the Initialize repository button or
    option 2B: I open the Source Control with clicking the branch-like icon on the left bar and then click the Initialize repository button or
    option 2C:
        i) I open a terminal in VSCode
            a) ctrl+shift+J on german keyboard or
            b) ctrl+` on english keyboard or
            c) in menu Terminal>New Terminal
        ii) the path is now my new folder and I initialize a git repository with typing in terminal: git init
3) I type git status in terminal to check if it's ok
4) I create something eg. readme.md or index.html and save
5) I add the files to the staging area (aka. index) by typing in the terminal
    a) git add .  or
    b) git add index.html
repeat 3)
6) I commit the staged files by typing git commit -m 'initial commit'
repeat 3)
It is ready to push to gitHub

Alice's Second Task:
I create a new repository on gitHub and push the existing local one to that
1) I open github in a browser and log in
2) I go to the repositories tab and click the new button on the right
3) I type a name without spaces eg. test_project  a) I can give a description and leave it public and then create, don't worry readme .gitignore and licence
4) On the quick setup page I choose the "push an existing repository from the command line" and copy or note the first line: git remote add origin https://github.com/olivabigyo/test_project.git
5) I go back to the teminal and add remote the existing local repository as origin to the newly created one on gitHub
    i) type or paste that first line: git remote add origin https:// github.com/....
    ii) Don't worry about the second line: git branch -M master  I guess it just renames the branch to master, from 1st October the default name will be main and notmaster https://github.com/github/renaming
    iii) type the third line as well to actually push it:
        a) git push -u origin master or
        b) git push --set-upstream origin master
6) I type git log and git status to check if it's ok :)
Make sure you already committed else the push fails and the git log command says:
fatal: your current branch 'master' does not have any commits yet
Make sure you often repeat 6) in the future :)

Alice's Third Task:
I invite Bob to collaborate on this project
1) I go to the test repository on github and click on the Settings tab
2) I choose manage access on the left menu bar
3) I click on the Invite collaborator button
4) I type Bob's gitHub user name or Bob's email address and add Bob to the project

Bob's First Task
I accept the invitation and clone Alice's repository
1) I received an email from gitHub
2) I log in to gitHub else it won't work :)
3) I click the See Invitation link in the email
4) I click on the Accept Invitation button on the gitHub page
