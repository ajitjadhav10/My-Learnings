

What is GitHub- It is  a product that offers remote servers for us to host our Git projects

What is Git-  Git is a version control system that is downloaded on our computer that allows us to collaborate with others. 


**Part 1:**
Installing Git on Mac:
- For installing Git on Mac, we'll make use of [Hombrew](https://brew.sh/). Homebrew is an open-source software package that allows us to install software on macOS
  
- First, open your terminal and run the following command:

**/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"**

- It will ask for your password, enter it and go to the next step

- Now, you can install git using this command:

**brew install git**

- Once you've installed it, you can check the version of your Git, using this command:

**git --version**


Now that Git is installed, we have to set-up our git environment using the **git config** command:


**git config --global user.name "your_github_username"**

**git config --global user.email "your_email_id"**

Note: Enter your Github username and email id in the above command


You can use the following commands to setup your defaullt text editor and the colors of your git console.

**git config --global core.editor emacs**

**git config --global color.ui true**


Congratulations! Your git is now installed and set up!

Conclusion:
So in this article you have learned how to set up git on your MacOS for the first time. In case, you have any questions, write them down in the comments, I'll try and answer them to the best of my ability.


**Part 2:**

What is git commit?
- The contents of your commit are a collection of changes that you make to your files. A commit is a piece of addition to the code which you can share with other collaborators. **IMP NOTE:** There is no commit without a commit message.

- A good commit should have a:
    - proper commit message
    - the size of the commit should be appropriate, for eg, making a commit after 1 or 2 weeks does not make sense, because in this case, it will become extremely difficult to track          changes when you refer to the commit message in the future. Ideally, you should make a commit every time  you make any addition to the code (maybe every 2-3 hours of coding)

- What is Rebase?
    - In rebasing we move all the commits present in a branch to the master branch. Here the hash-id of the commits changes becasue their parent node has changed.

- How to cherry-pick a commit?
    - In case of cherry picking, in contrast to rebasing where we rebase all the commits of a branch onto the master we only pick the commits from the branches which we want to commit on the master branch too, hence it's called cherry picking. (for example: say we fixed some bug on one of the commits in a branch which we want to have on the master branch as well, in that case we'll use cherry-pick command)

    - The cherry pick command is as follows: git cherry-pick "hashidofthecommit"
    - eg: git cherry-pick 89ffc45
    - Here, '89ffc45' represents the has id of the commit.

