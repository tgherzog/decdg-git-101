
---

# Viewing the Commit Log (History) #

The History window is a list of every commit in the project.

![History window](assets/images/history-window.png)


???

* Click the clock icon at the top of the Git pane to see the commit history for
  the repository.
* You can also see each change in the file, line by line. This is why your commit
  message can be very brief.

---
count: false

# Viewing the Commit Log (History) #

You can click any commit in the history list to view its changes.

![History window](assets/images/history-window2.png)

???

* You can click any commit in the history list to view the changes made in that commit
* You can also click the link next to each file in the "diff" pane to open the file
  *from that commit,* which lets you "go back in time."

---

# Creating Tags

* .orange[Tags] allow you to label a commit to identify and reference later (e.g. "wdi-2021-apr")
* In RStudio tags show up in .orange[orange].
* Tags do **not** move as commits are made to the repository

![Tag example](assets/images/tag1.png)


???

* The *SHA* column in the History window contains a string that uniquely identifies each commit
  in a repository. But these are very difficult to read and type
* **Tags** provide a way to label commits with more intuitive names. They appear in orange
  in the History window
* You typically do not tag every commit, just important ones, like release versions
* Tags to **not** move as new commits are added to the repository.

---
count: false

# Creating Tags #

To create a tag:

.col-left[
1. Open the History window and select a commit
2. Double-click the **SHA** value, then right-click and choose "Copy"
3. Open the Terminal pane
4. Type `git tag *new_tag* *Ctrl-V*`

(replace *new_tag* with the name of your tag)
]

.col-right[
![Creating tags](assets/images/tag2.png)

]

???

* To create a tag in RStudio, you use a combination of the History window and the Terminal
* First open the history window, select the commit you want to tag, and double-click the **SHA**
  value in the display below. Then right-click to open the context menu and choose Copy
* Then switch to the Terminal pane and type `git tag` followed by the name of the tag you want,
  then type Ctrl-V to paste the SHA value you got from the History window.
* Then press Enter. In the History window you probably need to refresh to see the tag.

---

# Using Branches #

* .purple[Branches] are independent commit streams within a repo. They can be
  derivative of the main branch or of other branches.
* Branches are a bit like tags, except they move with every new commit and
  are shown in .purple[purple].
* Branches can be **merged** together and/or discarded.

![Tag example](assets/images/branch1.png)

???

* Branches are a very important feature in git. Branches let you create independent
  versions of your work without having to create separate repos.
* Every repo has at least one branch, usually called **master.**
* Branches are similar to tags except the branch moves every time you add a new commit,
  creating a separate history trail. Tags typically stay put as you add new commits.
* Here you can see our sample repo now has two branches: **master** and **working**
* Branches are usually initiated from the last commit--or **tip**--of an existing
  branch. But you can also create a branch from a previous tag or any previous commit

---

# Using Branches #

### Reasons to create a new branch ###

1. Keep development or staging work separate from the production (master) branch
2. Keep your work separate from that of other colleagues
3. Experimentation
4. Any reason at all ;)

???

Why would you want to create a new branch, as opposed to just keep commiting to
the main branch?

* A common scenario is to use the "master" branch for final or production work
  and create separate branches for the development of new releases. When new
  releases are ready it's simple to merge the branch with the new release into
  the master branch. At the same time, if you need to do a "hot fix" in production,
  you can do that without affecting work on the next regular release.
* If several colleagues are working on copies of the same repo, each colleague
  can create her or his own branch so you're not always overwriting each other's
  changes.  The team can decide if, what and when to merge.
* You just want to experiment on the repo without affecting the main commit history.
  Just start a new branch and do whatever you like. You can switch back later,
  merge your changes, or discard them.
* The only reason *not* to create a branch is basic efficiency. If you find yourself
  merging most of your branch-specific commits, that might suggest it's
  easier to save a step and just keep working on the branch you're merging into.

---

# Creating and Switching Branches #

.col-left[
* **New branch from current branch:** use the .blue[branch icon] in the git pane
* **New branch from previous commit:** use the Terminal pane:
  `git branch *new_branch_name* *COMMIT*`
* Switch branches with the .green[branch menu]
* Delete branches from the Terminal pane:
  `git branch -d *old_branch*`
]

.col-right[
![create a new branch](assets/images/branch-create.png)
]

???

* There are two ways to create a branch. The first is in the git pane by
  clicking the branch icon, circled here in blue. This is the easiest way to
  create a branch based on the latest commit of the branch you are on.
* You can also use the terminal window if, for example, you want to create
  a new branch based on a previous commit or tag. Simply type `git branch`
  followed by the name of your branch and the commit to branch from. The commit
  can be a SHA tag that you copy from the History window as discussed previously
  or it can be the name of any previously created tag or branch.
* To switch to a different branch simply choose the branch from the menu
  in the Git pane
* You delete a branch using the Terminal pane by typing `git branch -d` and
  the name of the branch. Again, you'll probably need to refresh the Git pane
  to see your changes.

---
