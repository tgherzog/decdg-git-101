
---

# Getting started with Git

### Identifying yourself

.col-left[
* Access the Terminal tab (or type Alt-Shift-R)
* Type `git config --global --list`
]

.col-right[
![global config-user settings](assets/images/config-user.png)
]

--

.col-left[
* Type:

````
git config --global user.name "Your name"
git config --global user.email "your_address@worldbank.org"
```` 
]

???

* Okay, so let's get started. For the purposes of this tutorial
  we're assuming you have already installed RStudio and Git for Windows,
  which is how RStudio implements git.
  * RStudio can be installed via Software Center
  * Ask Tony if you need help installing Git for Windows, not sure about this
  * Mac Users are on your own, but help via Google is fairly straight-forward
* The first thing you need to do is identify yourself in git's global
  settings. This ensures that in the commit log people can see who you are.
  This is *not* used for authentication or logging into anything.
* In RStudio, access the Terminal tab, or type Alt-Shift-R
* Now type: `git config --global --list`. The terminal will show you git's
  global settings that apply to all projects. Right now you are only
  interested in the *user* settings.
  * PS: if the terminal window pages the output, use the space key
    to go to the next page and press "q" to quit (those aren't obvious)
* Type `git config --global user.name "your name"` and
  `git config --global user.email "your email"` (obviously substituting
   your name and address). This will set your name and email for all
   projects
*  Notionally, you should use your World Bank email address, but you can
   also use your personal address if you work on personal projects
   separately.
 * You can also set your name/email at the repository level
   by leaving out the `--global` option if you just want to change settings
   for one project.

---

# Creating New Git-Enabled Projects

*For projects that start life on your local computer*

**In RStudio:**  Choose .blue[**File > New Project > New Directory**]
and select .green[**Create a git repository**]

.half-size[
![new RStudio Project](assets/images/new-rstudio-project.png)
]

???

* There are several use cases for how you might start a git repository.
* The first is for a new RStudio project that, at least to start, only
  lives on your local computer.
* In RStudio, choose **File > New Project > New Directory** and select
  **Create a git repository**
* This repository **only** exists on your local computer. You can decide
  later if you want to "push" it to a shared repository so that others
  can access or contribute.

---

# Cloning Shared Projects #

*For projects that will be shared or already exist*

1. If necessary, first reate the repository in GitHub/TFS (in your browser)
2. Copy the "clone" URL using "https"

![git clone](assets/images/git-clone.png)

???
* The second use case is to first create a shared repository
  somewhere, and clone it to your computer. This is what you want
  if you know in advance that others will need access, or if you
  want to work on a project that others already started.
* You start by first creating the shared repository, either in
  GitHub or TFS. Typically you do this in your web browser.
* Then find the "Clone" or "Code" button in the repository. There
  will usually be both an "https" and an "ssh" option. You generally
  want the "https" option as "ssh" is usually blocked on Bank computers.

---
count: false

# Cloning Shared Projects #

*For projects that will be shared or already exist*

1. If necessary, first reate the repository in GitHub/TFS (in your browser)
2. Copy the "clone" URL using "https"
3. Choose .blue[**File > New Project > Version Control > Git**]
4. Paste the URL in the first text box

.half-size[
![git clone](assets/images/rstudio-clone.png)
]

???
* Now go to RStudio and choose **File > New Project > Version Control > Git**
  and paste the URL into the first text box

---

# Adding Files to a Project #

![empty rstudio project](assets/images/tutorial-project-empty.png)

???

* Now that the project is created, most git operations will be managed in
  the "Git" tab in the top right section of the RStudio window.
* Strangely though, adding a new file to git is not possible in this tab!
  You have to use the Terminal pane for that.

---
count: false

# Adding Files to a Project #

![Git add](assets/images/git-add.png)

???

* Here, I have created a new RMarkdown file and saved it to the project.
  But that doesn't add it to the git repository.
* In the Terminal pane, type `git add` followed by the file name and
  press ENTER. Here's a tip: in the Terminal pane you can start typing
  the file name and press Tab to auto-complete it, which saves typing
* You'll likely need to click the Refresh icon to get the file to appear
  in the Git pane.


---

# Committing Files #

.col-left[
### Q: what is a "commit"? ###

**A:** A commit is a **snapshot** of changes to a repository.
]

???

* Adding new or modified files to a project doesn't save those changes
  to the project. You need to "commit" those changes.
* What is a commit? A commit is a *snapshot* of changes to a repository.
  It could consist of changes to a single file or changes across multiple
  files.
* Often a commit will just involve a single file. However, if you've changed
  several files and those changes only make sense when taken together, they
  should be part of a *single* commit, not separate commits for each file.
* Files must be *staged* before they can be committed. Staging is where
  you select which files you want to commit and which files you don't
  (you might want to commit these later, or not at all).
* A good metaphor is packing a bunch of books together to send them to a friend.
  First you select which books, go in the shipping box; that's staging.
  Then you seal the box and bring it to the post office; that's a commit.

--

.col-right[
![Git commit package illustration](assets/images/commit-packaging.png)
]

.col-left[
### Q: what is "staging"? ###

**A:** staging is selecting which new or changed files to include together
in a single commit.
]

---

# Committing Files #


![Git commit RStudio](assets/images/commit-rstudio.png)


???

* In RStudio, the Staged column in the Git pane shows you which files
  have been staged, and allows you to stage or unstage files.
* So to commit a set of changes, first select the checkboxes next to the
  files you want to stage, then click the Commit button.
* If a file you want to commit isn't listed, you either need to add it
  via the command line as discussed earlier, or there are no changes
  to the file. Try clicking the Refresh button if you think the Git pane
  might be out of date.

---

# Committing Files #

.col-left13[
* Click Commit to commit your staged files
* Provide a **brief** commit message
]

.col-right23[
![Git commit message](assets/images/commit-message.png)
]

???

* When you click the Commit button you get a window to preview the commit
  and type a message for the log.
* The commit message should be very short, just a few words.
* Remember that people can easily see your actual
  changes no matter what you type, so there's no point in describing every detail.


