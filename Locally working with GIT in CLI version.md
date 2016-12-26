### Overview

* Git is a Distributed Version Control System ([DVCS](https://en.wikipedia.org/wiki/Distributed_version_control))
* You can work remotely with a remote git repository _(like the way you work with Subversion)_
* Or you can work locally (e.g. in your PC) with a local git repository _(this is very different from Subversion)_

### Preparation

1. Start your git command line interface
2. Create a directory (or you can use an available directory if you like). Here I create a new directory name `local_git`

 `$ mkdir local_git`

 From now on I will call this directory `working directory`

3. Change directory to the working directory

 `$ cd local_git/`

4. Initial settings

 `$ git config --global user.name "<example_user>"` //Set your name

 `$ git config --global user.email "<example@example.com>"` //Set your email, remember to use an appropriate email

 _These information will be logged as the author when you make a commit_

 You can check the settings also

 `$ git config --global --list`

### You will need to remember these things

1. Always read and make sure you understand the output of every command you run
2. If there is a command that you don't understand, you can use `--help` option to ask git about that command

 e.g. `git branch --help`


### Let's begin working locally with git as simple as possible

1. Firstly, you need to change the working directory into a git repository (also called **initialize a git repo**)

 `$ git init`
> You will see some output like:   
`Initialized empty Git repository in C:/xampp/htdocs/local_git/.git/`

 * Now you have got a local git repository which is ready to control your code's versions in your PC
 * Your local repository has a default `branch` named `master`
 * When the local repository is initialized, you will be switched to that branch: `/c/xampp/htdocs/local_git (master)`

 **From now on, to make things easy to understand, I will work in the default `master` branch**

2. Create a new file in the working directory _(or you can modify, delete some existing files)_

 `$ vi work_locally.txt`

3. Check the status of your local repository (also called `see untrack files`)

 `$ git status`

  > `On branch master`   
    `Initial commit`  
 `Untracked files:`  
    `(use "git add <file>..." to include in what will be committed)`  
          `work_locally.txt`  
 `nothing added to commit but untracked files present (use "git add" to track)`

4. Stage (add) the file to make git know that you want to commit the file

 `$ git add work_locally.txt`

 > `On branch master`   
`Changes to be committed:`   
  `(use "git reset HEAD <file>..." to unstage)`   
        `new file:   work_locally.txt`    

 _You can use `git add .` to add all new and modified files_

5. Commit changes to the local repo

 `$ git commit -m "first commit to local repo"`

 >`[master (root-commit) 9da90ac] first commit to local repo`   
 `1 file changed, 1 insertion(+)`   
 `create mode 100644 work_locally.txt`   

 _About `-m "some_text`" option in the command:_   
  * It is the option for you to write a commit message
  * It is a MUST that you write a message when you commit
  * Using `#issue_number` to link it to an issue (relating to working remotely with git)

6. Check commit log in local repository

 `$ git log`

 >`commit 9da90ac6900f6e0b8fedb443c86c16a74d413a1b`   
`Author: example_user <example@example.com>`   
`Date:   Wed Jul 6 20:16:37 2016 +0700`

 >   `first commit to local repo`

Here you have done a simple cycle to commit code to the local repo.

### Conclusion

* By working with a local repo, you can work even there is no internet to connect to a remote repo  
 _(As with SVN, you cannot commit your changes if there is no internet connection)_

* In actual working, you will need a remote repository to collaborate with your co-workers also.   
 Then you will need to make a connection between your local working branch and a remote branch.  
So that you can pull changes from the remote branch to your local working branch as well as push your changes to the remote branch.  
But because this post is about **Locally working with GIT**, we don't focus on that topic.
