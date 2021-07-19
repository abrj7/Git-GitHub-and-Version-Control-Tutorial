
 
 ## Introduction.
This tutorial is a complete guide to get going with [Git](https://en.wikipedia.org/wiki/Git), GitHub and understanding Version Control. Sometimes you don't always work on replit. Lets say you have to work on a project locally on your computer, using VSCode, and later you need that code on replit to share it with a friend or submit an assignment. This would be really tedious if everything was done manually, but now, along with Replit and Git/GitHub, this is a very easy task.  

## Prerequisites.
Because this tutorial is for general purposes, I am going to ask you to install __Hyper Terminal__. To use __Git__, we need a terminal, on __Mac__, its different, on __Windows__, its different. So to generalize things, go ahead and install __Hyper__ so that you can follow along. Also, to use Git, we need to install Git, so do that also.
#### [Install Hyper](https://hyper.is/).
#### [Install Git](https://git-scm.com/downloads).

## GitHub
#### Git and GitHub are the same thing, except that Git uses commands and everything happens locally, and is updated into your GitHub account. Everything you can do on Git, can be done directly on GitHub, but explanations for both interfaces will be done simultaneously.

___
## Version Control.
__What is Version Control?__. The answer is on the words itself. When you have a code file that you are consntantly working on, you continously need to keep updating the code. Let say I have a code file like this:
```py
def func(name):
  print(name)

func("Leo DiCap")
```
This is version 1 of your code uploaded to your repl, but later, as your code progresses, you change it into this:
```py
def intro(name:str, age: int):
  print(f"Your name is {name}, and you are {age} years old.")

intro("Leo DiCap", 46)
```
Now this is vesion 2, but lets say, you don't like this bit of code, and you want to go back to the previous version. To do that, you can just ask Git to rollback to version 1, and you are all set. This is Version Control in its simplest form.

![image](https://storage.googleapis.com/replit/images/1626380943172_381661e61a7e970ca74c9d7f89ed0ab5.png)

## Quick Setup.
Lets get started on Version Control with Git. To begin, open up a HyperTerminal Window:

![image](https://storage.googleapis.com/replit/images/1626381119261_a6387ca521f4f077f4715c52adb1c8a4.png)

Firstly, I am going to go into my Desktop, and make a sample directory for this project using the commands `cd` and `mkdir`:
```py
blurred@DESKTOP-MCER0B0 MINGW64 ~
$ cd Desktop/

blurred@DESKTOP-MCER0B0 MINGW64 ~/Desktop
$ mkdir sample_dir
```
You should see a folder with the name of "sample_dir" on your desktop. Now `cd` into the "sample_dir" directory and create three files, using the touch command: `f1.txt`, `f2.txt`, `f3.txt`.
```py

blurred@DESKTOP-MCER0B0 MINGW64 ~/Desktop
$ cd sample_dir/

blurred@DESKTOP-MCER0B0 MINGW64 ~/Desktop/sample_dir
$ touch f1.txt f2.txt f3.txt
```
Now, write some random sentences in the txt files for reference. Ofcourse in the real world, it is code, but for now lets keep it simple.
![image](https://storage.googleapis.com/replit/images/1626381960204_477bf3295d0c74efc209b38e55a4b8ca.png)

To use Git now, we initialize it using `git init` which will create a git file in your directory. Now we are all set up.

## Version Control with Git.
Now, to use Version Control we need to track changes on the files. To do that, we bring all the files we need to track onto the stagin area. To see untracked files, use the `git status` command, and all the files in red are untracked. To add on the staging area, we use `git add`. For now, we will only add `f1.txt`. So far:
```py
blurred@DESKTOP-MCER0B0 MINGW64 ~/Desktop/sample_dir
$ git init
Initialized empty Git repository in C:/Users/blurred/Desktop/sample_dir/.git/

blurred@DESKTOP-MCER0B0 MINGW64 ~/Desktop/sample_dir (master)
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        f1.txt
        f2.txt
        f3.txt

nothing added to commit but untracked files present (use "git add" to track)

blurred@DESKTOP-MCER0B0 MINGW64 ~/Desktop/sample_dir (master)
$ git add f1.txt
```

Now `git status` will show `f1.txt` in green. Lets commit these changes using `git commit -m "<message>"`. You might need to use a `git config` command to authorizie. To see all the commits, use `git log`
```py
blurred@DESKTOP-MCER0B0 MINGW64 ~/Desktop/sample_dir (master)
$ git commit -m "first commit"
[master (root-commit) 0ea04f3] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 f1.txt
```
`git status` now shows `f2.txt` and `f3.txt` as red. Lets add them all into the staging area using `git add .` and now the status should be green. Finally, once again, commit the files, `git commit -m "committed f2, f3"`.

#### NOW. There is a big issue. You had commited these files onto your repository, but mistakenly, you fell asleep on your keyboard and your file is now all gibberish. 
![image](https://storage.googleapis.com/replit/images/1626385086220_03fab60661e11d5a3af3f0a419205df6.png)

This version is now destoyed. How do you fix it? That is where our "savior" comes in: VESION CONTROL.
 *que dramatic music*.

On `git status` our modified file is red. That is because it is not comitted. Now to check the difference, we use the command: `git diff`. Th red shows the previous version, the green shows the changes.

![image](https://storage.googleapis.com/replit/images/1626385478859_e6427e2a93be9b1defa97db001634e22.png)

But to actually rollback, we will use `git checkout f1.txt`, and our file is restored.

![image](https://storage.googleapis.com/replit/images/1626385629301_1183cddbfa881ad6d7e4dd66e79b05b6.png)

A simple visualisation:

![image](https://storage.googleapis.com/replit/images/1626385859037_f9aa033dac85d04ad46d5f3d3a00a5cd.png)

## GitHub and remote repositories.
#### If you don't have a [GitHub](https://github.com/) account, go ahead and make one.
Remote repositories(repo for short) are basically hosted on GitHub. To create one, click the plus button on your GitHub account and click "New repository".

![image](https://storage.googleapis.com/replit/images/1626553993589_d8038a0e2347e2d049bc56b82afb7fea.png)


Now [create a new repository](https://github.com/new) by the name of "Sample", and give a description of anything. After you've done this, you will be greeted by a page that shows you how to set up a repo from the command line:

![image](https://storage.googleapis.com/replit/images/1626555498094_e0640de43413d9001627aa502fb3e531.png)

_We_ are going to push an existing repository from the command line. To do so, first copy the link on the top of the screen. 

Next, in the command line, to add all the commits we did on the __*Local Repository*__, we use the command, `git remote add origin <the link you copied.>`. The word origin in the command can be changed to anything, like `potato`, but `origin` is the programming convention, and its best to stick with it. The link in my case will be `https://github.com/OldWizard209/Sample.git`, so the entire command will be:

`git remote add origin https://github.com/OldWizard209/Sample.git`

Now that this is done, we need to push our _local_ rep onto the _remote_ repo that we created. This is done with this command:
`git push -u origin master`. The `u` command links up our repos and transfers/copies the files onto your remote repository. `master` basically is the main branch in your repo. Branches will be talked about in detail later. Next, if you reload you repo on GitHub, you should see all the files uploaded there:

![image](https://user-images.githubusercontent.com/68309049/126083768-994fbc9c-5f9e-4d38-81cc-b38639d581d8.png)

You will also be able to see your commets on `Insights > Network`:

![image](https://storage.googleapis.com/replit/images/1626646999939_7a80c1e6df828be5da262b80c59839f1.png)

## Gitignore.

Gitignore is a feature in Git that can allow you to prevent committing specific files. This is useful when you have personal API Keys, Tokens, Passwords etc, and you don't want to upload them on GitHub as other people can easily see them. To test Gitignore, lets create a sample directory with a bunch of files.

```py
blurred@DESKTOP-MCER0B0 MINGW64 ~
$ cd Desktop/

blurred@DESKTOP-MCER0B0 MINGW64 ~/Desktop
$ mkdir Project

blurred@DESKTOP-MCER0B0 MINGW64 ~/Desktop
$ cd Project/

blurred@DESKTOP-MCER0B0 MINGW64 ~/Desktop/Project
$ touch file1.txt file2.txt file3.txt secrets.txt

blurred@DESKTOP-MCER0B0 MINGW64 ~/Desktop/Project
$
```

Our secrets fies contains this:
```
API Key: 85NSWF41898RBXD5Q27FDNX
Password: jhYRFb5547!vv$
```
To actually use `gitignore`, we need to create a `gitignore` file, and put in all the files we don't need to show others. Gitignore files are created traditionally; `touch .gitignore`. Now in the gitignore file, we write down the names of the files we want to ignore.

![image](https://storage.googleapis.com/replit/images/1626648031225_0fd39d325aa6ed14bd27e1841d3eba05.png)

Now if we add all our files into the staging area, you will see that `secrets.txt` has not been added:

![image](https://storage.googleapis.com/replit/images/1626648452128_a6b2b7e34c3f25cf214a1c02d81f6c1c.png)


## Cloning
Cloning is one of the simplest concepts in Git. Cloning is simply getting any remote repository from GitHub and bringing it into your own local repository. To clone a repository, go to a particular repo, and copy the link on the left side of the interface:

![image](https://storage.googleapis.com/replit/images/1626648970574_47cd28a11b3624a226c622093e54b950.png)


Now to bring it into your local repo, run the command `git clone <link>`, in our case:

`git clone https://github.com/yenchenlin/DeepLearningFlappyBird.git`

## Branching and Merging.
Lets say you are working on a project and you ahve already commited once to your repo with the base essential code. Now you commit once more with the main logic of your program. But now you don't want to mess with the already written code, but you still want to try new features. 

Thats is when __branching__ comes in. You will create a new branch and start committing into that one without disturbing your main branch with all the meat and potatoes. Later, as your feature development in your side branch finishes, you can __merge__ the two commits creating one single file:

![image](https://storage.googleapis.com/replit/images/1626649943013_6497c5e3b33da4f48cd77d082d441579.png)

Now lets put this to the test. `cd` onto the `sample_dir` we made in the beginning. To create a new branch, we will use the `git branch <name of branch>` command. Lets do that in the terminal: `git branch change_plot`. If you want to check out the branches you have, just run the `git branch` command.

But we are still on the master branch. To switch branches we use `git checkout change_plot`. And now if I change some text from the files, it will still be the same in the master branch.

### `change_plot` branch:
![image](https://storage.googleapis.com/replit/images/1626650777759_4d84fb34b805d47295178f242d49016f.png)

### `master` branch:

![image](https://storage.googleapis.com/replit/images/1626651204651_1516a478c6b37a26237b78b558d4818b.png)

Make sure to `add` and `commit` before changing branches.

Now if we want to merge the two branches, we use the `git merge change_plot` while _in_ the master branch. Similarly, if you want to merge two branches, you can do that while being in a specific branch. Now if we put this up into the remote repo, `git remote add origin https://github.com/OldWizard209/Sample_Dir.git`, and go into the `Insights > Network`, we will see our beanches, and merges:

![image](https://storage.googleapis.com/replit/images/1626651838978_f568e9076c815a670a600d0a9dfe92f5.png)

## Forking and Pull Requests.
Lets say you work in a team and you need to collaborate with your team members. But the problem is, you own a repository and your team members can't change anything in it. This is where Forking comes in.

Forking allows other users to take a copy of your repo, and clone it into their own local repository, make changes to to it. After this they can commit the changes, and push them into her remote repository. Now if they want to bring the changes into _your_ repo, they have to make a __Pull Request__.

A Pull Request is like a suggestion or a branch created by another user. If the owner is OK with the changes, they accept the Request and merge it with their own branch. To create a Pull Request, you have to go to the Pull Request tab and create one from there.

## GitHub Repos with Replit.

Replit provides Version Control in the command line as well as in the user interface tab on the left. You can import an existing GitHub repo by navigating to the 'Version Control'. After making changes, you can even commit and push. 

### Creating Repos:
![image](https://storage.googleapis.com/replit/images/1626676394169_998e5ce23d1c41009b74d46915d29cc0.png)


### Commiting And Pushing
![image](https://storage.googleapis.com/replit/images/1626676460954_3b7913d15c30af953b8da5ecfee339ce.png)

But to do this, you have to first connect GitHub on REPLIT. Do this by going to `Profile > Edit > Connected Services > GitHub`:
![image](https://storage.googleapis.com/replit/images/1626676648176_e6c2c38b55295c46e5c56fedc3a99042.png)
