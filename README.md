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

## git push origin master

You are ready to push your first commit to the remote repository. The push here is for pushing your changes which requires a branch to push to call it origin and then specify the branch name master (the default branch that always exists on any repository).

So git push origin master will take the local commit that you made in the above sections and upload it to the remote server on github for other people to collaborate.

````
git push origin master
````

What's next?

Now that you know how to make your first commit and push it to the remote repository here are some other commands that you should know to start working on a team project.

## git pull

Suppose you are now another dev working on the same repository so you'll have to use this command to pull in the changes that you just pushed to the repository before making any commits. If you don't pull then GitHub will yell at you that you need to pull first.

````
git pull
````

## git checkout -b "new-branch"

You'll need this command too often while collaborating on a project that has more than one devs working on it. It creates a new branch for you with the name of the branch stated in the inverted commas (another gotcha here is the hyphen separated name for the branch which is necessary).

````
git checkout -b "new-branch"
````

There is (master) written after the name of the folder where you are running the command. That (master) is the default branch that gets created in every repository. If you see (master) in your command line then the `git checkout -b "new-branch"` will create a new branch based from the master branch. In other words, the branch you check out to will be based on the branch name you see in the command line so be careful about that.

Once you have checked out to a branch you'll be able to work in a detached environment having all the files from master. This way if you mess something you just go back to master branch and you'll have the initial files back. Many professional devs like to work like that.

more...
