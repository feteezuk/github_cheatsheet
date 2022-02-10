# github_cheatsheet
github cheatsheet based on Coursera Class

GITHUBcoursra

GIT CCOMMANDS:

1. ls -l .git ==> shows database of GitHub files changes and 
The git directory acts as a database for all the changes tracked in Git and the working tree acts as a sandbox where we can edit the current versions of the files.
2. 
GIT PROJECTS
1. Working Tree - contains current state of the project along with any changes we’ve made
    1. ls -l ==> Checks state of current workin tree
2. Git Directory - contains history of all files and changes
3. Staging area - contains changes marked to be in the next commit
TRACKED FILES STATE
1. Modified - made changes to a file but HAVE NOT committed yet(add, change, delete content)
2. Staged - the file has been marked with changes and ready to be committed. After modifying a file, we need to stage those changes and then commit them afterwards.
3. -Committed - changes get stored in a snapshot 
4. 

BASIC GITHUB WORKFLOW
1. Create new folder ==> mkdir new_folder
2.  cd into folder ==> cd new_folder
3. Initialize repo ==> git init
4. Check config ==> git config -l
    1.  RESPONSE:
    2. credential.helper=!aws codecommit credential-helper $@
    3. credential.usehttppath=true
    4. core.editor=nano
    5. user.name=Jonathan
    6. user.email=feteezuk@gmail.com
    7. init.defaultbranch=main
    8. core.repositoryformatversion=0
    9. core.filemode=true
    10. core.bare=false
    11. core.logallrefupdates=true
5. Create new file ==> touch all_checks.py
    1. Make changes to new file
6. Git add * ==> add new file to staging area
7. Git commit -m “add message” ==> commit to be ready to be pushed
    1. Every time u commit with message, u can read the message later
    2. -You can’t commit with an empty commit message.
8. Git add * ==> make new changes and add back to staging area
9. Git commit -m “add message” 
10. Git log ==> shows log of commit history

Commit message style guide for Git

The first line of a commit message serves as a summary.  When displayed
on the web, it's often styled as a heading, and in emails, it's
typically used as the subject.  As such, you should capitalize it and
omit any trailing punctuation.  Aim for about 50 characters, give or
take, otherwise it may be painfully truncated in some contexts.  Write
it, along with the rest of your message, in the imperative tense: "Fix
bug" and not "Fixed bug" or "Fixes bug".  Consistent wording makes it
easier to mentally process a list of commits.

Oftentimes a subject by itself is sufficient.  When it's not, add a
blank line (this is important) followed by one or more paragraphs hard
wrapped to 72 characters.  Git is strongly opinionated that the author
is responsible for line breaks; if you omit them, command line tooling
will show it as one extremely long unwrapped line.  Fortunately, most
text editors are capable of automating this.



WEEK 2 : USE GIT LOCALY
GOALS
1. - how we can undo some of our changes. The ability to revert previous changes is one of the most useful aspects of version control systems
2. -We can discard the changes made to a file, fix a commit that was incorrect and even roll back our project to an older snapshot.
3. Branches - se branches to work on an experimental feature without affecting the main code of our project. Support separate versions of a program that can't be merged together and much more
4. -what branches are, when and how to use them and how to deal with merge conflicts.

Skipping the Staging Area

￼

1. git commit -a -m "commit message” ==> Commit without using “git add” 
    1. NOTE: WILL ONLY WORK IF THE CHANGED FILE HAS BEEN ADDED BEFORE

WHA IS THE HEAD ? 
Git log==> HEAD is the pointer to the current branch
￼
EX.
commit ce5e2b7f7abfa6a1bba8308b03180d7b6a482c13 (HEAD -> main)
Author: Jonathan <feteezuk@gmail.com>
Date:   Wed Feb 9 18:10:07 2022 +0000

    commiting

commit 3c79504ec5b8e491a4817a1478f400a894f19cea
Author: Jonathan <feteezuk@gmail.com>
Date:   Wed Feb 9 17:30:08 2022 +0000

    changed all_checks.py

Getting More Information About Our Changes

1. Git log ==> Gives :
    1. list of commits,
    2.  commit message 
    3. author
    4. Date of change

2. Git log -p ==> Shows 1-4 and actual changes made to file
3. Git log —stat ==> which files were changed and how many lines added or removed
4. git show ce5e2b7f7abfa6a1bba8308b0318 ==> git show + commit id  will show u info about specific commit

Git add -p ==> SHOWS CHANGES MADE BEFORE ADDING CHNGES TO STAGING AREA

DELETE AND RENAME FILES
1. Git rm ==> removes files from being staged and tracked

Git rm workflow
1. Git add pppp.py
2. Git commit -m “adding ppp.py”
3. Git rm pppp.py
4.  git status
    1. On branch main
    2. Changes to be committed:
    3.   (use "git restore --staged <file>..." to unstage)
    4.         deleted:    pppppp.py
5. Ls -l ==> shows that it’s been removed 


HWO TO CAHNGE FILE NAMES WITH GIT
1. git mv all_checks.py one_check.py ==>changes name of all_checks.py to one_check.py
2.  git status
    1. On branch main
    2. Changes to be committed:
    3.   (use "git restore --staged <file>..." to unstage)
    4.         renamed:    all_checks.py -> one_check.py
3.  git commit -m "changed name of file" ==> must commit the change of file name
    1. [main 6b4860b] changed name of file
    2.  1 file changed, 0 insertions(+), 0 deletions(-)
    3.  rename all_checks.py => one_check.py (100%)
4. ec2-user:~/environment/scripts (main) $ git status
5. On branch main
6. nothing to commit, working tree clean


HWO TO Add GITIGNORE FILE
1. Touch .gitignore
2. Ls -la ==> lists all hidden files
3. Git add .gitignore
4. Git commit -m “add gitignore file”
5. 
6. Add files to not be seen in output


Advanced Git Cheat Sheet


Command	Explanation & Link
git commit -a	Stages files automatically
git log -p	Produces patch text
git show	Shows various objects
git diff	Is similar to the Linux `diff` command, and can show the differences in various commits
git diff --staged	An alias to --cached, this will show all staged files compared to the named commit
git add -p	Allows a user to interactively review patches to add to the current commit
git mv	Similar to the Linux `mv` command, this moves a file
git rm	Similar to the Linux `rm` command, this deletes, or removes a file
There are many useful git cheatsheets online as well. Please take some time to research and study a few, such as this one.
.gitignore files
.gitignore files are used to tell the git tool to intentionally ignore some files in a given Git repository. For example, this can be useful for configuration files or metadata files that a user may not want to check into the master branch. Check out more at: https://git-scm.com/docs/gitignore.
A few common examples of file patterns to exclude can be found here.

HOW TO UNDO CHANGES

HOW TO UNDO CHANGES BEFORE THEY ARE STAGED using ( git add )

1. STEPS
    1. Modify file
    2. Git status - in red
    3. Git checkout file_name -p ==>shows every change that’s been made and asks if u want it to be changed

How to undo changes

git checkout restores files to the latest stored snapshot, reverting any changes before staging.


BRANCHING AND MERGING

What is a branch at the most basic level is just a pointer to a particular commit. But more importantly, it represents an independent line of development in a project. Of which the commit it points to is the latest link in a chain of developing history

he default branch that Git creates for you when a new repository initialized is called master. All of our examples and development have taken place on this branch so far. The master branch is commonly used to represent the known good state of a project.

When you want to develop a feature or try something new in your project, you can create a separate branch to do your work without worrying about messing up this current working state

By creating a new branch, we can experiment without breaking what already works.

Creating New Branches

1. Git branch ==> lists branches
2. git branch new-feature==> adds new branch called “new-feature”
3. Git checkout new-feature ==> switches to new branch

￼

1. Git checkout -b new-feature ==> switches to new branch and goes to new branch
 The HEAD is moved to the relevant commit on the specified branch.

1. How to Delete a branch
2. Git branch -d name_of_branch

HOW TO MERGE BRANCHES -Merging combines branched data and history together.
1. git branch
    1.   main
    2. * new-feature
2. git checkout main ==> switch to main branch
    1. Switched to branch 'main'
3. git merge new-feature ==> merge new files to main branch
    1. Updating 6b4860b..015c755
    2. Fast-forward
    3.  new_file.py | 1 +
4. Git log ==>
    1. -commit 015c7550d941262
    2.  (HEAD -> main, new-feature)***
    3. Author: Jonathan <feteezuk@gmail.com>
    4. Date:   Wed Feb 9 19:27:13 2022 +0000
    5. 
    6.     adding new_file.py

Merging combines branched data and history together.


Git Branches and Merging Cheat Sheet


Command	Explanation & Link
git branch	Used to manage branches
git branch <name>	Creates the branch
git branch -d <name>	Deletes the branch
git branch -D <name>	Forcibly deletes the branch
git checkout <branch>	Switches to a branch.
git checkout -b <branch>	Creates a new branch and switches to it.
git merge <branch>	Merge joins branches together.
git merge --abort	If there are merge conflicts (meaning files are incompatible), --abort can be used to abort the merge action.
git log --graph --oneline	This shows a summarized view of the commit history for a repo.

WORKING WITH REMOTES

how to work with GitHub and other remote repositories.

Being able to use remote repositories allows us to effectively collaborate with others. Our collaborators can be sitting in the same office as we are or they can be thousands of miles awa

Basic Workflow with Remote Repos’
1. Git clone git@github.com:feteezuk/health_checks.git ==> clones GitHub repo 
2. cd health_checks/ ==> go into cloned repo
3. ls -l or ls-a ==> check the files in cloned repo
4. git commit -a -m "updated readme file"      ==> make change to readme and commit file                         
    1. [main f9532dc] updated readme file
    2.  1 file changed, 3 insertions(+)
5. git push
    1. Enumerating objects: 5, done.
    2. Counting objects: 100% (5/5), done.
    3. Compressing objects: 100% (2/2), done.
6. Git pull ==> pulls changes too the repo

The git push command gathers all the snapshots we've taken and sends them to the remote repository.

git clone URL	Git clone is used to clone a remote repository into a local workspace
git push	Git push is used to push commits from your local repo to a remote repo
git pull	Git pull is used to fetch the newest updates from a remote repository


1. Git clone git@github.com:feteezuk/health_checks.git ==> clones GitHub repo 
2. -git remote -v ==> DEFAULT NAME IS ORIGIN for remote repo
    1. origin  git@github.com:feteezuk/health_checks.git (fetch)
    2. origin  git@github.com:feteezuk/health_checks.git (push)
3. Git remote show origin ==> Shows a lot of info 
    1. -* remote origin
    2.   Fetch URL: git@github.com:feteezuk/health_checks.git
    3.   Push  URL: git@github.com:feteezuk/health_checks.git
    4.   HEAD branch: main
    5.   Remote branch:
    6.     main tracked
    7.   Local branch configured for 'git pull':
    8.     main merges with remote main
    9.   Local ref configured for 'git push':
    10.     main pushes to main (up to date)
4. Git branch -r ==> shows branches that git is currently tracking
5. 

To make a change to remote branch:
Pull the remote branch, merge it with the local branch, then push it back to its origin.

1. Git remote show origin
    1. -* remote origin
    2.   Fetch URL: git@github.com:feteezuk/health_checks.git
    3.   Push  URL: git@github.com:feteezuk/health_checks.git
    4.   HEAD branch: main
    5.   Remote branch:
    6.     main tracked
    7.   Local branch configured for 'git pull':
    8.     main merges with remote main
    9.   Local ref configured for 'git push':
    10.     main pushes to main (local out of date)
2. Git fetch ==> copies changes in remote repos to remote branches to get any changes other did
3. Git log origin/master ==> shows history of previous commits
4. Git status ==> shows if there is
5. Git merge origin/main ==> merges any changes
6. 
7. 
8. git pull instantly merges while git fetch only retrieves remote updates. 
9. Git fetch ==> will not merge automatically
10. Git pull ==> merges branches automatically


Updating the Local Repository

1. Git pull ==>fetch the remote copy of the current branch and automatically try to merge it into the current local branch.
2. Git log -p ==> shows the changes made in the git pull 

git remote	Lists remote repos
git remote -v	List remote repos verbosely
git remote show <name>	Describes a single remote repo
git remote update	Fetches the most up-to-date objects
git fetch	Downloads specific objects
git branch -r	Lists remote branches; can be combined with other branch arguments to manage remote branches



Git push -u origin name_of_file ==> pushes code to remote repo

Merges

Git rebase ==> 

1. Git checkout main ==> switch to main brainch
2. Git pull ==> get and merge any changes from master branch
3. Git log —graph —oneline —all ***===> Very use full to see what going on with code
4. 



STEPS To clone Someone else’s Repo into your own: SSH
1. git clone git@github.com:noahgift/dockerproj.git ==> clone remote repository
2. git remote -v ==> Check where the origin is
    1. origin  git@github.com:noahgift/dockerproj.git (fetch)
    2. origin  git@github.com:noahgift/dockerproj.git (push)
3. git remote rm origin==> Delete origin 
4. Create new empty repo and grab link-git@github.com:feteezuk/health_check
5.  Git remote add origin git@github.com:feteezuk/health_check==> Add new origin
6. git branch -a ==> if branch labeled “main” does not exist, create it 
7. git checkout -b main ==> creates branch named “main” 
8. git push --set-upstream origin main ==> pushes files into GitHub
9. Make changes in your files
10. Git add *
11. Git commit -m “m”
12. Git push
