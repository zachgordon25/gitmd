# Git & GitHub

## Lesson Agenda

1. What is Git?
1. What is GitHub?
1. How do they work together?
1. Set up SSH
1. How do you make a repository and clone it?
1. Stage files
1. Commit files
1. Push files
1. Pull changes from remote repo
1. Create a github issue
1. Unmake a git repository
1. An introduction beyond the basics (branching merging), adding an SSH key, customizing your terminal to show your git branch
1. History an comparison of versioning tools

<hr>

## Note

Toady we have a lot of set up to cover. On a new job you'd typically get help with a lot of the set up we'll do today from the IT department or a Senior Developer.

## What is git?

![](https://imgs.xkcd.com/comics/git.png)

A version control system - a way to track changes in your computer.

![version control](https://i.imgur.com/sXyZ6nK.png)

Git does this for you "behind the scenes"!

## What is GitHub?

GitHub is a company that offers storage for your files. It offers a way for people to easily share their files through forking & cloning. In addition, collaboration is made possible by allowing multiple people to become collaborators on repositories.

## Who Uses It?

Companies who share their code: https://github.com/d2s/companies/blob/master/src/index.md

- Nasa:
  - https://www.nasa.gov/mission_pages/apollo/missions/apollo11.html
  - https://github.com/chrislgarry/Apollo-11
- Spotify:
  - https://github.com/zmb3/spotify
- YOU!

## Other Versioning Tools

You can read more information on this history of [file sharing from Wikipedia](https://en.wikipedia.org/wiki/File_sharing)
In the days of old, people used [FTP](https://en.wikipedia.org/wiki/File_Transfer_Protocol), [CSV](https://en.wikipedia.org/wiki/Comma-separated_values),and [SVN](https://en.wikipedia.org/wiki/Apache_Subversion).

Another popular cloud solution that is used with git, GitHub's competitor, is [Bitbucket](https://bitbucket.org/).

## How Do Git and GitHub Interact?

### Git

You work with **git** for your local tracking.

![git](https://i.imgur.com/JI8rNwP.png)

### GitHub

GitHub is a company that will store your documents "in the cloud". You can have access to your code from any machine from their company website: www.github.com.

![github](https://i.imgur.com/c92z3Wx.png)

### Your Part in Their Relationship

You play the most important part in this relationship. You have to tell **git** whether to track files. In addition, you can also tell **git** to send your work to **GitHub**.

You do all of this with **git** commands on your command line / terminal.

# Setup

For each repo, we'll follow a bunch of steps to get set up. Setup is typically fast!

## Common Git Commands

Git has some funny phrasing.

- When you want to get code onto your computer you `pull`\*
- When you want to send code to github (or elsewhere on the internet) you `push`
- If you want to make a copy of a repository on your computer(also known as local/locally) it's called `cloning`
- If you want to make a copy of a repository on github and store it on your account, that's called `forking` - note: `forking` is specific to github and is _NOT_ a git command

\* `pull` can also mean a request for someone to pull in your code - on github you may see something called `pull requests`

When you use bash (terminal shell) you are talking to your computer. There is a structure to the commands you tell it.

A git command has a minimum of 1 argument.

Git commands are always executed by first typing `git`

The first argument is the command (or verb), like

- `git init` (initialize a new git repository)
- `git push` (send the code to a remote location)

The second(+) argument gives the first argument context (when needed)

- `git add .` (add all files in this directory)
- `git pull origin main` (get all files from the url that has an alias of `origin`, from the branch `main`)

Lastly, flags can be added

- `git remote -v` (git show remote(s) and be verbose(give more detail))

Here is a table of our commonly used git commands:

| git | Argument | Flag(s)/Additional arguments |                                                                  Description                                                                   |
| :-: | :------: | :--------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------: |
| git |   init   |                              |                                                          Initializes a new repository                                                          |
| git |   add    |       `.` or filename        |                             Takes untracked files and adds them to the staging area so that they can be committed                              |
| git |  commit  |      -m 'some message'       |                             Takes a snapshot of files in the staging area/ saves this version of them as a commit                              |
| git |  remote  |              -v              | Shows the remote repositories associated with the local repository. Most repositories have an alias for their urls like `origin` or `upstream` |
| git |   pull   |        upstream main         |                                    Gets files from a url with an alias of `upstream` from its branch `main`                                    |
| git |   push   |          origin dev          |                                       Sends files to a url with an alias of `origin` to its branch `dev`                                       |
| git |   log    |          --oneline           |                              Shows a log of commits of a repo (--oneline shows a truncated message)_`q` to exit_                               |
| git |  status  |                              |                                        Shows the state of files in a repo (untracked, modified, staged)                                        |

Note: `fork` is not on this list because `fork` is not a git command; it is github-specific for copying a repository on github to a new location on github.

### Git VCS - Branches and Merging

Git is a VCS (Version Control System). There are a few popular ones, but git ends up being a top choice because of its branching and merging feature.

If we think back to our past projects(or term papers), when we wanted to implement some major changes to our code/text and failed our popular options were to

- `⌘Z` throughout our files and hope for the best
- Seriously contemplate coding out our project from scratch again

[Git's about page has 4 great reasons why it works so well for individuals and large teams.](https://git-scm.com/about)

- Frictionless Context Switching - Switch between branches, whenever! No worries!
- Role-Based Codelines - Have many versions of your code - Production, Development, Day-to-Day etc.
- Feature Based Workflow - Create a new branch for each feature
- Disposable Experimentation - if a branch doesn't work out, you can just walk away or toss it. It has no impact on the working code

You may be thinking 'this sounds too good to be true!' It's not! But there is a catch! Git requires changing the way we are used to working on projects. Which means it takes some time and practice to learn to use git.

![git workflow from git about page](https://i.imgur.com/MXiZRI0.png)

## SSH Key

- When you use `https` to connect to github, it will likely ask for your password often.

- If you get tired of always entering your github password, you can use the ssh URL (as opposed to the https URL) when cloning a repo

- You'll need to also add what's called an ssh key to github https://help.github.com/articles/generating-an-ssh-key/
- Now you can use the ssh url when cloning instead of https

Both will give you all the rest of the same features. It's just a matter if you'd like to spend more time setting up first or if you don't mind entering your password more often.

## Practice Making a GitHub Repo

### 2 Ways :octocat:

For both ways, let's make a folder on our `Desktop` called `github_practice`

`cd` into that folder in terminal

#### 1. Making a repo on GitHub first and cloning it locally

1. Go to your GitHub enterprise account and log in to your account.

1. Click on the plus sign next to your profile photo at the top-right corner of your page:

   ![new repo](https://i.imgur.com/u21yY3L.png)

1. Click on `New repository`

   ![new repo click](https://i.imgur.com/w9tkj8J.png)

1. Create a new repo by entering a name in the `Repository Name` field. Note that this name has to be _unique_ to your repository. Let's use the random name that they suggested for me: `repo-practice`

   ![repo name](https://i.imgur.com/j8Ex7hX.png)

1. You have the option of making this repo either a **public** or **private**.

1. Click on the "Initialize this repository with a README". A README file is just a blank document that is the default page that your repository displays. It is a markdown file and normally includes information that you provide about your application. What you are reading right now is a README file.

   ![readme](https://i.imgur.com/OMX3sah.png)

1. Click `Create repository`. You should be redirected to the newly made repo.

1. Click on the `Clone or download` button.

1. Copy the link (this is the direct link that is created by GitHub to your repo).

   ![clone and download](https://i.imgur.com/eQAy4O3.png)

1. Open your terminal - it's time to make a local copy of this GitHub repo!

1. In your terminal, navigate to the folder where you would like to keep the folder for this repo. Let's use that `github_practice` folder we created on our desktop

1. `cd` into `github_practice` DO NOT create a new folder for our repo, when we use `git clone` it will create a new folder for us

1. Type the git command `git clone` followed by the link to your repo.

   ![clone](https://i.imgur.com/SaOFuio.png)

1. That's it! Type `ls` to see your folder's contents. Your new repo should be there. Navigate inside the folder, type `ls` and confirm that you have a `README.md` file.

1. Go ahead and open the `README.md` in your text editor (Bonus! Do it from the command line!). You can write plain text in a markdown file. So you can send yourself a message! If you don't know what to write, go with a classic `Hello World!` , save this file.

1. In terminal type `git status`

1. `git add .` to add your file to be `staged` - this will tell git that you'd like to track this file's changes

**Note:** `git add .` adds everything in the current directory, including directories inside this directory. It's like a waterfall. It will never add files above where you are in terminal.

![](images/git_add_visual.png)

1. `git commit -m 'my first commit'` - this will take a 'snapshot of your file' and have a message attatched to it

1. `git push origin main` - this should send your changes to your github repo

1. Go back to the browser, refresh, you should see your updated readme!

1. Back in terminal type `git status` - it should now say there is nothing to commit

1. We can remind ourselves where we sent our work, type `git remote -v`

This will show you the name of the remote, by default it is called `origin`. Rather than typing `https://github.com/stuff/morestuff/blahblablah` every single time you want to connect with your repo, you just type `origin` instead - less typing = working smarter, not harder!

You'll also see the branch name, by default `main`, you can have many branches and their utility is amazing! In fact it is the branching of git that makes it a top choice. But for today, we'll just work with our main branch.

<hr>

#### 2. Making a local folder, turning it into a git repo, pushing it up to GitHub

1. Navigate to the folder where you're keeping the files for this lesson. Likely, you just need to `cd ..` back to the `github_practice` folder's root.

GOTCHA: Do not initialize a git repository inside of another git repository, do not make your root directory of your computer a git repository - this will confuse git and you won't be able to track or even open your files on github. Additionally, making your entire computer a git repository can siginficantly slow down your entire computer.

![](images/Gitception.png)

1. Create a new folder called `another_project` inside `github_practice` - make sure you are NOT inside the git repo you created

1. Navigate inside `another_project` and type `git status` (you should get an error). We need to ask git to track this folder, so let's tell it to do so.

1. Inside this folder, run the command `git init` (this tells git to track this folder). Type `git status` to see that there is no longer an error.

1. `touch README.md`

1. `code README.md` and type some text and save the file

1. in terminal, `git add README.md`, `git commit -m 'first commit'`

1. We now have a local git repo, we have to create a repo on GitHub and connect it. Navigate to GitHub and log in if you're not logged in already.

1. Create a new GitHub repo. Let's give it the name `another_project` (note that this is the same as our local file, but it does not have to be for it to work).

1. **Do not** initialize a README (we already made it on our own in our local repo).

1. a new page in github will appear with instructions. We'll follow them. Note - with bash commands you have to enter them one at a time.

1. Grab the first line and paste it in terminal it will be something like: `git remote add origin git@github.com:username/new_repo`

1. Confirm that you have the remote created by running the command `git remote -v`, you should see the URL you added. If you see nothing, then something went wrong.

1. Grab the second bash command from github, it should be something like `git push -u origin main`

1. Go back to GitHub and refresh your page. Your README file should now be pushed up from your local repo to your GitHub repo.

## Interacting with Other People's Repos

Sometimes we want to interact with another user's repo. We can safely do this by **forking** it.

**Forking** is the equivalent of making a copy to keep for ourselves.

<hr>

## Practice on Your Own

Learning git is hard! It's a pretty different way of tracking and moving files than we're used to. But practice will make it come naturally. We'll be using git and github every day so you'll get comfortable with it quite quickly!

## Unmake a git repository

What makes a git repository a git repository?

The hidden file `.git`

You can check if you are in a git repo by typing `git status`

You are NOT in a git repo if you get this message:

![not a git repo](https://i.imgur.com/gDdafBl.png)

You ARE in a git repo if you get a different message. Here is one sample one

![in a git repo](https://i.imgur.com/m3fYhmC.png)

If you are in the root of your git repository you can type `ls -a` to show your hidden files and you'll see a folder `.git`

You should NEVER edit inside this folder. Git is very sophisticated and the contents of this folder are automatically generated. Don't mess with the git magic or you may destroy your whole git repo.

With that in mind, what if you accidentally made something a git repo? Or you no longer want to have something as a git repo? You can `rm -r .git` to return your directory back into a normal repository.

<!-- ## See Which Branch You're On

Some people like seeing what branch their on/if they are in a git repository by having a message in the terminal prompt. In this case the main branch is listed in green:

![](https://i.imgur.com/ejthVDL.png)

If you too would like to have this. Go to this [github gist](https://gist.github.com/joseluisq/1e96c54fa4e1e5647940) and follow the instructions. -->

## A Brief History of Versioning tools

### Explain the difference between git and other versioning tools

- In the old days, people would use FTP (File Transfer Protocol) to send their files to central computer - The issue: 1. Two people (Person A, Person B) copy the same file from the remote repo at roughly the same time 1. They both make changes 1. Person A uploads their changes 1. Person B uploads their changes, overwriting Person A's changes
- The next step was to create a locking mechanism - How it worked 1. Person A would "check out" a file (like in a library) 1. Person B would not be able to check out that file until it was checked back in 1. Person A would make changes to the file and then check it back in 1. Person B could now check out that file - The issue - Person B would have to wait for person A to finish with a file to start work on it
- The next step was tools like CVS and SVN - How it worked 1. Both Person A and Person B could check out a file at the same time 1. Person A modifies the file and checks it back in 1. Person B modifies the file, tries to check it back in, but cannot 1. Person B must re-check out the file that now includes the changes made by person A 1. CVS/SVN will attempt to merge the changes together 1. As long as the changes made by both Person A and Person B are on different lines, this will succeed 1. Once the changes made by Person A have been merged with Person B's version of the file, Person B can now check in their file - The issue - If a person is not ready to check in a file, there is no way to keep track of the changes made to that file - If something goes wrong before checking the file back in, the user must, figure out what happened, go through an almost endless number of Undo commands in their text editor, or revert their file to version that is in the repository. A lot of work could be lost
- Git functions just like CVS and SVN, but it adds a local repository - This allows a user to keep a log of their local changes before finally pushing everything back to the remote repository - The user can also travel "back in time" to previous states that have been saved locally, but not yet pushed to the remote repository. This is great for when something goes wrong - The process: 1. Add files whose changes you want to be logged 1. Log the changes of the files that were added (called making a "commit") 1. Once all commits have been made, and you're ready to send your changes to the remote repo 1. "pull" any changes that have been made to the repo since you last synced your local repo with the remote repo 1. "push" your changes to the remote repo.
