# GitHub Tutorial

_by Andre Lara_

---
## Git vs. GitHub

### Git
Git is a type of code language used on the command line. It can serve as version control for your code because it saves how your code looked before you made a drastic change that caused an error and you want to get back to your old code, before the error. Even though Git is in the word Github, you **do not** need to use Github when using git. It is completely optional.
### Github
Github is where your code gets stored. Atlhough you have to set up a connection between Github and your repository so that you can see your code being stored in the cloud. You have to `add` `commit` and `push` before being able to see the changes you make to your repository. Even though most people use Github for storing their code, it can store many other documents and files. For example, it can hold the lyrics to different songs, legal files, architectural plans. If you are going to use Github you **have** to use git, it is not optional. 


---
## Initial Setup
### Account Setup for Github and Cloud9
If you don't already have a github account then you need to make one. Use an email that you already have and if you are from HSTAT use your school email. If you don't know it then it's first name + first letter of your last name + last 4 digits of your ID + hstat.org. Make sure to go to your email and verify your Github account.

### Cloud9 and Github Linking

Before continuing to work with Git and Github you have to setup a connection so that Git knows where you are pushing your work to. Here you will be making a SSH rather than a HTTPS key because for an HTTPS key you have to enter your username and password everytime you attempt to push something to Github. With an SSH key its a one time thing that will allow you to push your work without having to type in your username and password.
1.  First you have to open Github and go to settings. On the menu you have to look for SSH and GPG keys. Click on make a new key and then stop there. 
2.  Now you have to open up your cloud9 and sign,then click on the gear icon and go to SSH Keys. There you should see a code beginning with `ssh-rsa` or something close to that. Copy and Paste that key and go back to github. There you will paste the key. 
3.  Finally, you will have to go to back to cloud9 and open up the worspace that you want to make the connection between. In your command line type `ssh -T git@github.com`. It should give you back "Hi _your username_! You've successfully authenticated, but GitHub does not provide shell access." Then you're done a connection has been permanently made.


---
## Repository Setup

### Local Repository
Now that you have everything setup, its time to make your first repository. To begin you will want to go to cloud9 and open up your workspace. Once you're in your workspace open up the terminal and make sure you are in _username_:~/workspace. Never initialize git in your workspace, you'll always want to create another folder and then initialize git. Now we can create a folder called first-repo, type into the terminal `mkdir first-repo` and go into it by doing `cd first-repo`. Now that you created a new folder and you are in the folder, you're going to want to initialize git. You do this by using `git init`. That is basically how to create a local repository, lets take it a step further and do our first add and commit. Go back to the terminal and make sure you are still in `first-repo`. Next create a file and add some text to it. Use `touch` to create a file. Add some text into the file and then make sure cloud9 saves. If you were to type `git status` you would see that there is one untracked file, the one we made. To start tracking the file you can use the `git add` command. After typing this if you do `git status` again you can see that the file is now being tracked and is green instead of red. Now that the file has been added to the "stage" we can commit. Type `git commit -m "message"`, when writing a commit message it should be short and in the present tense. This is sort of like an unspoken rule of commit messages. Now we are done with the local repository.

### Remote Repository
To make a local repository we can use the same repository from before. However, for this you will have to open up Github and sign in to your account. Once you sign in you will see a + sign in the top right corner. Click that and then choose new repository. When naming this new repository you have to name it the same exact name that your repo on cloud9 was called. Once you name it and press continue there will be a bar that says HTPPS and SSH. Make sure you have SSH highlighted and then you can copy and paste the portion of code that says "...or push an existing repository from the command line". After this step you should be able to push your files from your local repository on cloud9 to your remote repository on Github. Lets try it out. Go into your file and change the text in the file. Now you have to `add` and `commit` again, however this time you have to use the `git push` command. Once you use that command it will give you a bunch of text in response but really its just publishing your work to the cloud or github in other words. Now refresh your github page and you should see your changes along with your github commit message. If you ever have an error use `git remote -v`. You should see a line starting with fetch and then a line with push. The push line is what matters because it tells you where you are pushing your cloud9 files to.


---
## Workflow & Commands
### Git Status
This command is the go to command. The command is written like so: `git status`If you come accross an error you will most likely want to git status to try and see what the problem in your code is. The git status command will let you know of any untracked files and which files need to be committed. This won't tell you of any errors in your code though, that is what the command line is for.
### Git Add
The use for this command is to "add" your files to the staging area. The way git commands were taught to me is that git itself is a photographer and github is the album where photographs are stored. When you use `git add` you are bringing all your files onto the stage for their picture to be taken. The pictures however is not taken yet, so the files are just waiting there for something to happen. There are different variations of the `git add` command. For example, you could do `git add .` which adds all the files that have been changed from your last commit/add. You can use `git add file` which adds a specific file that you have in your repository. Finally, you can do `git add --all` which literally adds all the files in your repository.