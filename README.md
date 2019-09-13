# Git Practice

This tutorial assumes that you have Git set up, and that it's configured properly (username, email, etc).

For this tutorial, we're going to try three things:
1. Make changes in the master branch  
2. Make changes in a branch on the remote  
3. Creating a new branch and pushing it  

To get started, fork this repo in the top right and clone your fork to your computer.

```
git clone <repo url>
```
Or copy the comnand that GitHub gives you. 


NOTE: at any point, you can type `git status` that will give you a pretty good idea of what's going on with your environment in that instance.


# Making changes in the master branch

Once you have this cloned on your computer, we're going to make some changes, stage it, commit it, then finally push it.


### Making some changes

Within your working directory, create a new file titled `initial.txt`, and put some text inside.

Add this to your index (staging area).
```
git add initial.txt
```

Now, commit that file to your local repo.
```
git commit
```
It will prompt you to insert a commit message using your default text editor. Optionally, you could use this one-liner.
```
git commit -m "Commit message here."
```
At this point, you should see your commit when you use `git log`. Note that it's not in the remote (in this case, GitHub) yet! 

### Making some more changes

We're going to change the contents of the file, because it turns out we didn't put enough (arbitrary) text within. 

Edit your `initial.txt` file with some more text. Now, if you type `git status` you should now see a new section that sort of looks like this:
```
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   initial.txt
```
Follow the same workflow above to commit this to your local repo.

### Pushing our changes

We're now happy with our file. Let's push it to our remote so our friends and family can see our hard work. 

Since we cloned the repo, our remotes are going to be set up for us. Thus, all we need to do is a `push`.
```
git push
```

NOTE: If you create a new repository locally with `git init` and you want to push it to a remote, you'll have to manually set up your remote URL and upstream destination.


# Making changes to a branch on the remote

There should have been a branch in the original repo, titled `practice-branch`. Check to make sure you see it on your forked repo. You can also verify it with `git branch -r`, which will show you all the branches on the remote.

Now that you've verified that the branch `practice-branch` exists, we're going to switch to it.
```
git checkout practice-branch
```
This command first checks to see if that branch exists locally. If it doesn't it will search your remotes and finds it in your remote with the matching name. If it's found, it sets up your local branch to track the remote branch.

Now follow the steps above and create a file, make some changes, stage it, commit it, then push it. 

You should see your changes in your branch (should be at `$REPOURL/tree/practice-branch`).

# Creating a new branch and pushing it

We're now going to create a new branch, and push it to the remote. 

We'll use a command similar to the one above.
```
git checkout -b other-branch
```
Where `other-branch` is your branch name. There are subtleties to this command, but the gist of it is that it will create a new branch at your current commit, titled `other-branch`. For example, if you started off on `practice-branch`, then you'll create a new branch based on the tip of that branch.  


Now, follow the steps above again to create a file, make some changes, stage it, and commit it. 

The last step, pushing it, changes because we must set up our remote for this branch. Use the following command.

```
git push -u origin other-branch
```
Let's break this command down. `-u` is a flag (which is a shortcut for `--set-upstream`) that allows you to set the upstream, `origin` is the name of the remote, and `other-branch` is your branch name that you want to push. This sets up the branch to track the remote. 

And that's it! 

# Beyond

There are a ton of other things you can do with git, which I cannot even begin to cover here. Once you get used to the basics, you'll find yourself in situations where you'll need the more advanced tools; don't be afraid of taking that dive!  

# Resources

[Resources to learn Git](http://try.github.io/)
