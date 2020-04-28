git-commands-headstart
# Git commands - Headstart

Based on "Git and Github - must know commands to make your first commit" at https://dev.to/juni/git-and-github---must-know-commands-to-make-your-first-commit-333c

## git status

Check if there are already some changes tracked in the repository by git? git status will list any files that are changed.

````
git status
````

## git add .

This is the first command that you'll run after making some changes to the project files.

The command analyzes all the repository files and adds all modified and new (untracked) files in the current directory and all subdirectories to the staging area (a.k.a. the index), thus preparing them to be included in the next git commit which I'll explain in the next lines. Any files matching the patterns in the .gitignore file will be ignored by git add .

````
git add .
````

## git commit -am "your commit message"

git commit -am adds the changed files into a commit with a commit message as stated inside the inverted commas(in the hading). Using the option -am allows you to add and create a message for the commit in one command


````
git commit -am "your commit message"
````

The ***-a*** flag is used in git to add all the files to your commit and then you'll have to run another command where you write your commit message.

The ***m*** flag is used for connecting a commit message to your commit for example `git commit -m "your message"`.

Be very careful when using this command because it will add all the changed files to your commit which you may not want in many cases. You can add individual files to the stging area by using git add. For example git add file1.js image.png index.php to add only "file1.js", "image.png" and "index.php" to the staging area and then you can create a commit with git commit -m "your commit message".

Hence git commit -am "your commit message" is the second command that you must know.



