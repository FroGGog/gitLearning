# GitHub
---
We are learning git and github right now, and this is our training task.
---

## 1 Getting to know GitHub

Git is a **version control system** that helps track changes in a project. This tool can be used for both individual and team work.


Git allows you to save changes locally and, if necessary, return to previous versions of the project. You can also create a remote copy on a hosting platform that works with Git and share the result with others.<br>


In order for Git to start tracking changes in the project, the folder with the files of this project must be made a Git repository.<br>
* **git init**


## 2 Starting working with Git.

//Main commands to start git repository and etc

## * File .md how to work with them

//Few words about main rules and syntax

## File statuses. maybe put in second paragraph
```mermaid
graph LR;
    A(Untracked)-->|git add| B(Staged);
    B(Staged)-->|git commit| C(Tracked);
    C(Tracked)-->|changes| D(Modified);
    D(Modified)-->|git add| B(Staged);
    B(Staged)-->|changes| D(Modified)
```

## 3 Branches and all about it.

//Lets create some branches and try to split info in maybe more paragraphs?
