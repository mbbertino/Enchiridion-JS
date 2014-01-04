# Git Basics

Git is an extremely popular version control tool and is at the core of services like GitHub[^00] and Heroku[^01]. While sometimes rather confusing and at all times frighteningly powerful, it's a fantastic tool for recording incremental changes to your project's files and synchronizing those changes across multiple machines, servers and developers. Because of its distributed nature, it's generally simple to recover lost files and data, even if a team member's entire hard drive is lost.

### Installation
OS X comes prepackaged with Git, but to download the latest stable version, simply run
	
	$ brew install git
	
in your terminal. Again, bear in mind that the `$` simply represents your terminal prompt, and shouldn't be entered into the command line.

If you're using GitHub (which you should be), you'll want to look into the setup process in the GitHub documentation. Although HTTP authentication is the recommended setup, I still prefer the SSH key-based auth.[^1]

### Learning Git

There are many, many resources for learning Git. One of the most approachable is [http://try.github.com](). I suggest you go through all of the steps in the tutorial. After that, a more advanced tutorial on Git branching can be found at [http://pcottle.github.io/learnGitBranching/]().

### Most Used Commands
Here are some basic commands, taken almost verbatim from the Git documentation pages (run `git help` in your terminal to view the same docs)

##### Basic Commands:

    init       Create an empty git repository or reinitialize an existing one
    add        Add new or modified files to the staging area
    rm         Remove files from the working directory and staging area
    mv         Move or rename a file, a directory, or a symlink
    status     Show the status of the working directory and staging area
    commit     Record changes to the repository

##### History Commands:

    log        Show the commit history log
    diff       Show changes between commits, commit and working tree, etc
    show       Show information about commits, tags or files

##### Branching Commands:

    branch     List, create, or delete branches
    checkout   Switch the active branch to another branch
    merge      Join two or more development histories (branches) together
    tag        Create, list, delete, sign or verify a tag object

##### Remote Commands:

    clone      Clone a remote repository into a new directory
    fetch      Download data, tags and branches from a remote repository
    pull       Fetch from and merge with another repository or a local branch
    push       Upload data, tags and branches to a remote repository
    remote     View and manage a set of remote repositories

##### Advanced Commands:
    reset      Reset your staging area or working directory to another point
    rebase     Re-apply a series of patches in one branch onto another
    bisect     Find by binary search the change that introduced a bug
    grep       Print files with lines matching a pattern in your codebase
    
For more info on any command, just type `git help <command>`. With the exception of the advanced commands, you'll use most of these everyday. Learn them well!


### Example flows

While it's beyond the scope of this simple guide to teach all of Git, let's at least look at a few flows that you'll use again and again. Please not that the output of each command isn't printed here. Make sure to *carefully* read the output of each command in your terminal


#### Create a new repo
	$ git init
	$ git add .
	$ git commit -m "Initial commit"
	
This will turn the current directory into a Git repository, stage all of the files in the directory, and commit them with a commit message of "Initial Commit"


#### Commiting changes to a file
	$ git status
	$ git diff
	$ git add .
	$ git commit -m "Updated Example text"

This will inspect what files have changed with `git status`, show the line-by-line difference (only for tracked files) with `git diff`, add all files (be careful, this will add both tracked and untracked files) using `git add .`, and commit the changes.
	

#### Pushing changes to GitHub

	$ git push origin master

This will push your local master branch to the master branch on a remote server nicknamed "origin", which will almost always be GitHub.


#### Creating a branch based off of master

	$ git checkout -b cool_new_feature
	
	// change some files and commit them
	
	$ git push origin cool_new_feature
	
This created a new branch based off of your current branch (be careful creating and switching to branches… untracked files will follow you to the new branch!). You would them make changes, commit them (neither are shown in this example), and the push them. This would create the `cool_new_feature` branch if it doesn't exist, and push the new commits to the new branch on origin.


#### Pulling from a remote branch

	$ git pull origin cool_new_feature
	
This will fetch and merge the specified branch into the current local branch.


### Getting help
If and when you get stuck with Git, search on Stackoverflow. The best questions and answers will always be upvoted and are generally trustworthy. It's safe to say that you will almost never run into a Git problem that hasn't been thoroughly discussed and correctly answered on Stackoverflow.

[^00]: [GitHub](https://github.com)
[^01]: [Heroku](https://heroku.com)

[^1]: [GitHub SSH setup](https://help.github.com/articles/generating-ssh-keys)