# GitHub Classroom Guide for Students

Note: This material is heavily adapted from Jacob Fisksel's own guide: https://github.com/jfiksel/github-classroom-for-students

This is a guide for students to setup Git, GitHub, and RStudio and to ensure that all the components are able to properly interact together. Each component is an independent tool and they are not always used together. However, these components work well together when learning and applying data science. 

For useful videos see [Git setup for Windows](https://youtu.be/F_fPEMnr1OQ) or [Git setup for Mac](https://www.youtube.com/watch?v=kbmSZwK0k-A&t)

### Steps for getting setup with Git, GitHub, and RStudio
0. **Read a little about Git/GitHub/R** to understand better why we are using this particular combination of tools (https://happygitwithr.com/big-picture.html)
1. **Install Git**. Directions for both Windows & Mac here: http://happygitwithr.com/install-git.html. Windows users should follow Option 1 in 6.2. Mac users can follow Option 1 in 6.3 if comfortable, otherwise follow Option 2. 

2. **Register for account on GitHub (https://github.com/).** We recommend using a username that incorporates your name (jfiksel, mtaub, lrjager)

3. **Download R** (https://cran.r-project.org/) and **RStudio** (https://www.rstudio.com/)

4. **Set up options in Git.** We tell `Git` our name and email so it knows who to attribute changes to. In `Rstudio`, click on `Terminal` in the lower left pane and input the following two commands to setup your name and email.

    1.  `git config --global user.name 'Jane Doe'`
    2.  `git config --global user.email 'jane@example.com'`

    The following command will confirm whether it worked or not: `git config --global --list`

5. **Set up a PERSONAL ACCESS TOKEN**. In order for your local machine to make changes to your GitHub account there needs to be some way to authenticate that you are the actual owner of the account. GitHub no longer allows authentication using the password you used when you set up your account online and prefers you use something call a PERSONAL ACCESS TOKEN (PAT). 
    1. Go to https://github.com/settings/tokens and click “Generate new token." *MAKE SURE TO CHOOSE A CLASSIC TOKEN*
        1. Choose a date after the end of the semester or no expiration
        2. Choose "repo","user", and "workflow." 
        3. Temporarily copy your PAT to your clipboard
    2. Store your PAT so that you don't have to input it each time you access GitHub
        1. Install an R package to help with PAT storage. In your `RStudio Console` tab, type `install.packages("gitcreds")`
        2. Type `gitcreds::gitcreds_set()` and paste your PAT when prompted. 
        3. Check that it worked by inputting `gitcreds::gitcreds_set()` This will allow you to connect to GitHub from RStudio in the next step.

6. **Set up a new repository and make sure you can connect to it via RStudio** (https://happygitwithr.com/rstudio-git-github.html). You can ignore some of the items in 12.1 because we will skip Connecting directly to GitHub. We will always access GitHub via RStudio in this class. 

    **Note: If you would like visual aids see https://book.cds101.com/how-to-stage-commit-and-push-to-github-using-rstudio-server.html**

**Congratulations! You've succesfully set up all the software we need for the course!**

7. **(Optional) Read some Git basics** (https://happygitwithr.com/git-intro.html)

## Steps for downloading and editing assignments from GitHub Classroom

The previous steps were for setting up the software in general. The next steps are specific to how you should manage using Git/GitHub/RStudio for **this** class

See [How to clone, edit, and push homework assignments with GitHub Classroom](https://youtu.be/pAcMgGbCtQw) for a helpful video.

1. Have a folder specifically for this class (call it something like econ122). Within this folder, I would recommend a folder titled **home** for your activities, as well a folder titled **problem_sets**.

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
        |---econ122
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

4.  In RStudio, go to File -> New Project. Click Version Control, then Git. Paste the link you just copied into the Repository URL box. Leave the Project directory name blank. **Create this as a subdirectory of your problem set folder.** An RStudio project should now open up, which will allow you to start working on your problem set. You will probably see a blank console screen. However, in RStudio you should also see a list of all of the files available. Click on whatever file you want to edit (probably the .Rmd file) and edit away. If you save and close R Studio and want to go back to editing your project, open up R Studio, then go to File -> Open Project. Navigate to the project directory and double click on the .Rproj file.

5.  After you make changes to the problem set, commit them. What are commits you ask? Commits are essentially taking a snapshot of your projects. For example, if I make changes to a code so that it prints "Hello world", and then commit them with an informative message, I can look at the history of my commits and view the code that I wrote at that time. If I made some more changes to the function that resulted in an error, I could go back to the commit where the code was originally working. This prevents you from creating several versions of your problem set (PS1-v1, PS1-v2, ...) or from trying to remember what your code originally looked like.

You can make commits using the GIT toolbar in RStudio (in RStudio make sure the toolbar is visible by doing View -> Show Toolbar). Click the Commit button in the GIT toolbar dropdown menu. Check the files that you want to commit, enter your commit message, then hit Commit. 

Two things about committing. One, you should commit somewhat frequently. At minimum, if you're doing a problem set, you should make a commit each time that you've finished a question. Two, leave informative commit messages. "Added stuff" will not help you if you're looking at your commit history in a year. A message like "Added initial version of hello-world function" will be more useful.

6.  At some point you'll want to get the updated version of the assignment back onto GitHub, either so that teachers/TAs can help you with your code, or so that it can be graded. You can do this by using a command called `git push`. If you are ready to push, you can again click on the GIT toolbar dropdown menu in RStudio, and then click `Push branch`. You can also do this after you commit in RStudio by clicking Push in the top right corner of the Commit pop-up box.

**Note: You don't need to PUSH everytime you COMMIT. You only need to PUSH when you want to sync up with GitHub.**

### Resources
* [Happy Git and GitHub for the useR](http://happygitwithr.com/)
* [The Unix Workbench](http://seankross.com/the-unix-workbench/)
* [Interactive learning guide for Git](http://learngitbranching.js.org/)
* [GitHub Guides](https://guides.github.com/)
* [Git setup for Windows (video)](https://youtu.be/F_fPEMnr1OQ)
* [Git setup for Mac (video)](https://www.youtube.com/watch?v=kbmSZwK0k-A&t)
* [How to clone, edit, and push homework assignments with GitHub Classroom (video)](https://youtu.be/pAcMgGbCtQw)
