git-commands-headstart
# Git commands - Headstart

Based on "Git and Github - must know commands to make your first commit" at https://dev.to/juni/git-and-github---must-know-commands-to-make-your-first-commit-333c

Based on "Git Reverting to Previous Commit – How to Revert to Last Commit" at https://www.freecodecamp.org/news/git-reverting-to-previous-commit-how-to-revert-to-last-commit/

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

## git reset

To revert to a previous commit, you must first get the commit ID. To do that, run the command below:

```
$ git log --oneline
```

To go back to a previous commit (e.g. ```5914db0```), you run the git reset command followed by the commit ID. That is:

```
$ git reset 5914db0
```

We've successfully gone back to a previous commit.

If you want to undo a commit and the all the changes made after that commit, you attach the ```--hard``` flag to your ```git reset``` command.

Let's test this out by reverting back to the first commit (e.g. ```89f6c3d```):

```
$ git reset 89f6c3d --hard
```

We're back to the initial state of the file at the point of the specified commit. All changes that were made to the file after that commit were deleted. When we check the commit log, we'll have just the first commit.

If you undo a commit and delete every file change that came after it, you might lose important changes made to your code by you and other teammates. This will also change the commit history of your project.

Luckily for us, there is way to recover the state of a deleted commit. You can learn more about that [here](https://www.freecodecamp.org/news/how-to-recover-a-deleted-file-in-git/).

```git reset``` will undo changes up to the state of the specified commit ID. For example, reverting to the second commit ID will undo changes and leave the state of the file as the state of the second commit.

You should use ```git reset``` when working on a local repository with changes yet to be pushed remotely. This is because running this command after pulling changes from the remote repo will alter the commit history of the project, leading to merge conflicts for everyone working on the project.

```git reset``` is a good option when you realize that the changes being made to a particular local branch should be somewhere else. You can reset and move to the desired branch without losing your file changes.

## git revert

To revert to the to the previous commit, run the git revert command along with the commit ID of the current commit.

In our case, we'll be using the ID of a third commit (e.g. ```882ad02```):

```
$ git revert 882ad02
```

The command above will undo the current commit and revert the file to the state of the previous commit.

Unlike the git reset command, the git revert command creates a new commit for the reverted changes. The commit where we reverted from will not be deleted.

```git revert``` will undo changes up to the state before the specified commit ID. For example, reverting to the second commit ID will undo changes and leave the state of the file as the state of the commit that comes before the second commit – the first commit.

```git revert``` is a good option for reverting changes pushed to a remote repository. Since this command creates a new commit, you can safely get rid of your mistakes without rearranging the commit history for everyone else.

So as you can see, ```git reset``` and ```git revert``` are not the same.

more...
