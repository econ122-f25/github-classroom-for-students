# GitHub Classroom Guide for Students

Note: This material is heavily adapted from Jacob Fisksel's own guide: https://github.com/jfiksel/github-classroom-for-students

This is a guide for students to setup Git and GitHub for use with GitHub Classroom. We use RStudio in our class, so we will give instructions on how to use RStudio to setup Git locally. However, this is not necessary.

### Steps for getting setup with Git, GitHub, and RStudio
1. Register for account on GitHub (https://github.com/). We recommend using a username that incorporates your name (jfiksel, mtaub, lrjager)

2. **Install Git.** Directions for both Windows & Mac here: http://happygitwithr.com/install-git.html. Windows users should follow Option 1 in 6.2. Mac users can follow Option 1 in 6.3 if comfortable, otherwise follow Option 2. Below, I show how you would access the terminal on a Mac, as well as how to enter the commands given in the link. Windows users should consult the video posted under Resources

3. Download R (https://cran.r-project.org/) and RStudio (https://www.rstudio.com/)

![Alt Text](http://g.recordit.co/ENAZXCmgs9.gif)

4. **Setup options in Git**. In you have a Mac, open up the shell in R Studio by clicking Tools -> Shell. If you don't want to enter RStudio, you can go to the terminal if you have a Mac (Applications -> Utilities -> Terminal) as shown above. If you have a Windows, open Git BASH, which you should have downloaded in step 3. Enter the three lines of code here: http://happygitwithr.com/hello-git.html, changing the first two lines to your own name and email (this should be the email associated with your GitHub account). Note that Windows users should read section 8.1 in the above link carefully. Below is an example of what this process looks like on a Mac:

![Alt Text](http://g.recordit.co/ibUp6dYimU.gif)

5. **Set up authentication method**. Git is a local program while GitHub is a remote repository. In order for your local machine to connect to GitHub, you must set up an authentication method. These include
    1. (recommended method) The default Git installation now comes with a credentials manager that manages the authentication for you. You will get prompted for your login information when you first try to clone a repository
    2. Create a personal access token (https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token)
    3. Set up SSH (https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)

6. Follow the instructions here (http://happygitwithr.com/push-pull-github.html) to ensure you can connect to GitHub from your computer. Here are step-by-step GIFs from a Mac that help visualize this process.

### Make a repo on GitHub

Below we make a repository and copy the link so that we can get the repository onto our own computer.

![Alt Text](http://g.recordit.co/Uw0QIT8XhR.gif)

### Clone the repo to your local computer

![Alt Text](http://g.recordit.co/0eLLGCclcO.gif)

### Make a local change, commit, and push and confirm the local change propogated to the GitHub Remote

![Alt Text](http://g.recordit.co/f24e9xvo6d.gif)

**Congratualations! You've succesfully pushed your changes to GitHub!**

## Steps for downloading and editing assignments from GitHub Classroom

1. Have a folder specifically for this class (call it something like econ122_fall_2021). Within this folder, I would recommend a folder titled **home** (which will dynamically update the course materials) , as well a folder titled **problem_sets**.

Here is a basic illustration of how my directory structure looks.

```
Users
│
│
│
└───mgelman
    │
    │
    │
    └───CMC
        │
        │
        |
        |---econ122_fall_2021
            |
            |
            |
            |---home
            |
            |
            |---problem_sets

```

2.  For problems sets and group projects, I will give you a link to an assignment, via the class page. This will happen for each new assignment. Note that after you accept an assignment for the first time, we will send you an invite to join the classroom organization as a member. Please accept this. You will probably get an email with the invitation, but you should also see a link at the top of your main GitHub page. Here is an image of what you should see after clicking the link:

![Alt Text](img/accept-assignment.png)

3. Enter the problem set repository on GitHub (this is online--GitHub is different from Git!). Click “Code” and copy the link in the box to your clipboard.

4.  In RStudio, go to File -> New Project. Click Version Control, then Git. Paste the link you just copied into the Repository URL box. Leave the Project directory name blank. Create this as a subdirectory of your problem set folder. An RStudio project should now open up, which will allow you to start working on your problem set. You will probably see a blank console screen. However, in RStudio you should also see a list of all of the files available. Click on whatever file you want to edit (probably the .Rmd file) and edit away. If you save and close R Studio and want to go back to editing your project, open up R Studio, then go to File -> Open Project. Navigate to the project directory and double click on the .Rproj file.

Here is a visualization of cloning an assignment onto your computer through R Studio on a Mac:

![Alt Text](http://g.recordit.co/nKeMWFh4vS.gif)

5.  After you make changes to the problem set, commit them. What are commits you ask? Commits are essentially taking a snapshot of your projects. For example, if I make changes to a code so that it prints "Hello world", and then commit them with an informative message, I can look at the history of my commits and view the code that I wrote at that time. If I made some more changes to the function that resulted in an error, I could go back to the commit where the code was originally working. This prevents you from creating several versions of your problem set (PS1-v1, PS1-v2, ...) or from trying to remember what your code originally looked like.

You can make commits using the GIT toolbar in RStudio (in RStudio make sure the toolbar is visible by doing View -> Show Toolbar). Jacob Fiksel has made a video on how to do this here (available under resources--How to clone, edit, and push homework assignments with GitHub Classroom), and you can read how to do  this in RStudio in more detail here: http://r-pkgs.had.co.nz/git.html#git-init.  Click the Commit button in the GIT toolbar dropdown menu. Check the files that you want to commit, enter your commit message, then hit Commit. Here is also a short GIF showing how to do this:

![Alt Text](http://g.recordit.co/96UWQ9Avy2.gif)

Two things about committing. One, you should commit somewhat frequently. At minimum, if you're doing a problem set, you should make a commit each time that you've finished a question. Two, leave informative commit messages. "Added stuff" will not help you if you're looking at your commit history in a year. A message like "Added initial version of hello-world function" will be more useful.

6.  At some point you'll want to get the updated version of the assignment back onto GitHub, either so that teachers/TAs can help you with your code, or so that it can be graded. You can do this by using a command called `git push`. If you are ready to push, you can again click on the GIT toolbar dropdown menu in RStudio, and then click `Push branch`. You can also do this after you commit in RStudio by clicking Push in the top right corner of the Commit pop-up box. Here is a visualization of both options:

![Alt Text](http://g.recordit.co/TkOnIVLttw.gif)

**Note: You don't need to PUSH everytime you COMMIT. You only need to PUSH when you want to sync up with GitHub.**

### Obtaining and pulling a shared repository

This class has a repository that includes all the files related to this class. The most important files you'll be using are the in class **activities**. The repository will be updated throughout the semester, and it will be useful to constantly have the most updated materials on your local computer. You can do this by first cloning the repository, and then pulling in changes. Here are the steps.

1. Open a new project in RStudio and use the repository **https://github.com/econ122-f21/home.git**. Create it under the econ122 folder you setup earlier.
2. To pull in changes, goto the **Git** tab and click on **Pull**. If you get an error about merge conflict, don't freak out! This can happen if you edit locations in files that are also changed by me. I'll be doing my best to ensure this doesn't happen, but if it does, simply contact your me to get it worked out. Or even better, try to google the error message and try to fix it yourself!

### Resources
* [Happy Git and GitHub for the useR](http://happygitwithr.com/)
* [The Unix Workbench](http://seankross.com/the-unix-workbench/)
* [Interactive learning guide for Git](http://learngitbranching.js.org/)
* [GitHub Guides](https://guides.github.com/)
* [Git setup for Windows (video)](https://youtu.be/F_fPEMnr1OQ)
* [Git setup for Mac (video)](https://www.youtube.com/watch?v=kbmSZwK0k-A&t)
* [How to clone, edit, and push homework assignments with GitHub Classroom (video)](https://youtu.be/pAcMgGbCtQw)
