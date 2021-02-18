
---

# Fundamentals of version control and git

### Q: What is "version control?" ###

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

???


---

# How git is different from "track changes"

.col-left[
.red[**track changes**] works on one file at a time.

.green[**git**] works on multiple files collectively.
]

.col-right[
![sample git repo](assets/images/sample-git-repository.png)
]

---

# How git is different from "track changes"

.clear-block[
.col-left[
With .red[**track changes**] everyone shares the same file (tough to merge).

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
