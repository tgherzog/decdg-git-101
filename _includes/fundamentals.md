
---


# Fundamentals of version control and git

### Q: What is "version control?" ###

???

* Version control is a tool that keep track of changes you make to a project as you make them
* Over time you end up with a complete record of all changes made to a project, when and by
  whom, and you can "revert" to any previous point in the project history.
* You can think of sort of like "track changes" in Word, or "suggestion" mode in Google
  Docs, except much more extensive.

--

.col-left[
**A:** A tool that tracks discrete changes made to a project as you make them.
]

--

.col-right[
![track changes](assets/images/like-track-changes.png)
]

.col-left[
Same concept as "track changes" in Word, but in a much larger sense
]


---
class: phasing

# When would you use version control? 

.col-left[
Many different use cases: software projects, data management, websites,
research papers, presentations.

* Data management: [JHU](https://github.com/CSSEGISandData/COVID-19) or [Washington Post](https://github.com/washingtonpost/data-police-shootings)
* Dashboards: [Open SDG](https://sustainabledevelopment-rwanda.github.io/)
* Websites: [Open Data Toolkit](http://opendatatoolkit.worldbank.org) or [ESG](https://esgdata.worldbank.org)
* Tool development: [Statistical Performance Indicators](https://github.com/worldbank/spi)
* Research: [ESG Gaps](https://worldbank.github.io/ESG_gaps_research/)
* Presentations: [this one](http://tgherzog.github.io/decdg-git-101)
]
???

* Version control is suitable to many different kinds of projects. For example, software projects
  where you need to track changes to source code across a bunch of different projects.


---

# How git is different from "track changes"

.col-left[
.red[**track changes**] works on one file at a time.

.green[**git**] works on multiple files collectively.
]

.col-right[
![sample git repo](assets/images/sample-git-repository.png)
]

???

* The biggest difference between git and "track changes" is that "track changes" works
  one one document at a time, where git works on an entire project. You can make changes
  to several different files, and add those files as a single "commit." 
* That way if you go back to a previous point in the commit log, the files at that point
  will be consistent with each other.
* This collection of files is called a **repository** or sometimes just a "repo".


---

# How git is different from "track changes"

.clear-block[
.col-left[
With .red[**track changes**] merging is difficult; you either share the same file or
"pass it around."

With .green[**git**] everyone works on their own copy and merges changes at will.
]

.col-right[
![sample git repo](assets/images/shared-repositories.svg)
]
]

You can even have multiple "remote" repositories
````
cd wbg-ogdtoolkit
git remote -v
origin  git@github.com:tgherzog/wbg-ogdtoolkit.git
toolkit tim@opendatatoolkit.worldbank.org:/usr/local/share/git/wbg-ogdtoolkit.git
````

???

* The other big difference is that with the "track changes" approach the whole team
  typically works on the same document simultenously, like a shared Google or Teams document,
  or even a file that you pass around via email.
* If you've ever tried to "merge" changes from even two different versions of the
  same file, you know this can be very hard.
* With Git you **always** work on a **local** copy of the repo, and "push" your changes to a master
  repo.
* You can even have more than one "master repository." Here are the settings for the git
  repository for the Open Data Toolkit at http://opendatatoolkit.worldbank.org. One
  repository lives in GitHub. The other one lives on the OGD toolkit web server, and
  when you commit changes to that repository, it triggers the site to regenerate.
  Yes, you can build entire sites in git.


---

# How git is different from "track changes"

.col-left23[
![sample commit history](assets/images/sample-history1.png)
]

.col-righti13[
Here is an example of the commit log from a repository that includes
changes from multiple authors.

Work happens in independent, parallel "branches" which "merge" when needed.


]

???

* Here is a good example of how git users can work together.
* This is the project history of an actual project. Each line is a "commit," or
  set of discrete changes to one or more files. We'll talk more about commits in just a minute.
  You can see the person who
  made the change and when they made it. You can select the commit to see details.
* In this example the 3 authors are working on independent "branches" as shown
  by the colored lines on the left. Tim's branch is shown in green, Tony's in
  beige and Andres in purple.
* We'll get to branches more in a few minutes. For now, the point is that
  git lets multiple team members collaborate while keeping their work streams separate until
  they are ready to merge them, if ever.


---

# Differences between "git" and "GitHub"

* .green[**git**] is software that you run **locally** on your computer.

* There are many different "git clients" (software programs), most of which
  are interchangable, many of which are open source.

???

* **git** is software installed on your computer
* You use git to work on a **local** personal copy of a repository.
* There are lots of different git clients you can choose from and for the more post they
  are interchangeable. In this course we use the git commands built into R Studio

* **GitHub** is a website for hosting shared repositories

* **TFS** is a Microsoft Azure, cloud-based platform that works on the same principles as
  Github and provides some of the same features. The big difference between TFS and Github
  for us is that TFS is provided through ITS, is available only to Bank staff (not the public)
  and can therefore be used for "official use."

--

* .blue[**GitHub**] is a website for hosting public or private git repositories
  so you can **share** them with others.

* GitHub includes extra features (website hosting, project management, wiki, issue tracking, etc)

--

* .red[**TFS**] is an Azure-based platform which provides many Github-like features,
  suitable for internal Bank use
