# Git Good Guide
## Setup and Basic Overview
This repo is designed to help teach the work flow of using git in your group project. when using git there are essentially four versions of the code base to be concered with. Your branch of code exists in two seperate versions, one on your local machine and the other on GitHub. The master branch has the same setup, where there is a version on your local machine and a version on Github. Git is designed for you to work on the code in your own branch without causing issues in others code.

#### What is a Branch, and why do I need it.
A branch is when you take an existing code base and make a copy of the code. This copy will not effect the original or 'Master' branch, allowing you to make changes to the code with out the risk of causing issues in the original code.

It also makes it easier for multiple people to work on the same code base and not overwrite or cause conflicts in each others code. Then when you are ready to merge your code with the original code git can help make sure every one's code does not overwrite each other.

#### Creating Your Own Branch
To make your own branch run the following command

`git checkout -b [name_of_your_new_branch]`

the -b in the command will make sure you create a branch and switch to it after its creation

#### Checking What Branch You are on.
When starting this guide you will need to be working on your own branch. To check what branch you are on run `git branch`. This will display all the branches you have on your local computer, with a star next to the branch you are working from, or working branch.

<pre>* My_Branch
  master
  Bob_Ross_Branch</pre>

#### Getting on Your Branch
To switch to another branch run the following command

`git checkout [name_of_your_branch]`

**You should never make changes to the code base while on the master Branch**

**Make sure you read the results after you type in every command.**

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-0.jpg" />


### Step 1: Checkout master

The First Thing we need to do is checkout the master branch. We will be getting the latest version of the master branch on our local machine

**Common Issues**
You can not swap to another branch if you have not done a `git add` and `git commit` to your code. Make sure you read the results after you type in every command.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-1.jpg" />


### Step 2: Pull From master

In Git when we move code around, like uploading or downloading we call it Pushing or Pulling. Both tasks acomplish basically the same thing, but the difference is the direction of the data flow. Here we will be doing a Pull from the master. This command will Pull the code from GitHub and update your local Master version to be identical.

**Never write code while on the master branch or push to the master branch**

**Common Issues**
Sometimes when you try to pull from master it won't let you until you have done an add and commit. This typically means changes were made on your local master branch. Never make changes on the master branch.

To fix this run `git add` and `git commit`. **DO NOT RUN GIT PUSH!!!!** Never push to master.

 <img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-2.jpg" />

### Step 3: Switch Back to Your Local branch

When we merge two branches we have to choose what branch will be recieving the changes and which one will be referenced. We want the Master Branch to be the reference and the Personal branch to recieve the changes. Because of this we need to swap back to your Personal Branch.

 <img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-3.jpg" />

### Step 4: Merge Your Code with Master

Now that we have a local version of the most up to date Master Branch we can merge our local version with the Master version. While on your local branch run `git merge master`.

**Be sure to read the messages that come after this command to ensure you don't have merge conflicts.**

If you have merge conflicts look at each file it says a conflict has been found (you can ignore your bundle files as those will be fixed after you run Gulp).

Merge conflicts look like this:


<pre>
&#60;&#60;&#60;&#60;&#60;&#60;Head
  var someCode = 'example'
========
  var someOtherCode = 'different example'
&#62;&#62;&#62;&#62;&#62;&#62;Master
</pre>


The part between the `>>>>>>>>Head` and the `=======` is your local version of the code, and the part between the `======` and `<<<<<<<<Master` is the code from the master. Talk to who ever the other code belongs to and figure out whose code should be there, make sure you remove the 3 lines that were added when you are done, being the `>>>>>>>Head`, `=======`, and `<<<<<<<<Master`.

**Tip**
If you press `ctrl-shift-f` on windows or `cmd-shift-f` on mac you can do a search for every instance of `>>>>>>>Head` in your whole project, making it easier to find conflicts.

 <img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-4.jpg" />

### Step 5: Push Your Code to GitHub

Now that you have merged your code with the Master branch you can push your code up to GitHub. Run `git add .`, `git commit -m "message"`, and `git push`.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-5.jpg" />

### Step 6: Submit A Pull Request

After you push go to your group's repository page on GitHub. A new yellow bar with a green button on the right that says 'Compare & Pull Request' should appear. If fit does not click the New Pull Request button that is highlighted below.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-6-1.jpg" />

A new page will load. If you clicked the 'Compare & Pull Request' button then it should look very similar to the image below. Add any comments you would like to make regarding the pull request then click the Green 'Create Pull Request' button in the highlighted 2 section.

If you had to click the gray 'New pull request' button then you will need to click the second gray drop down on the page below. The drop down on the left should read master and the one on the right should read your branch name.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-6-2.jpg" />

**Merge conflicts**
The second page will also inform you if there was any unresolved merge conflicts. If there are then you will need to redo all above steps. Be sure to read all the results from when you run commands. They often tell you exactly what you need to run to resolve the issue.

Once you have submited your pull request talk to or send a message to your mentor and they will review the pull request and approve it. Once approved the online master branch will have your new code availible for the rest of the group.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-6.jpg" />


### Step 7: Pull Down the New Master code

Checkout the master branch by running `git checkout master` and pull using `git pull`
