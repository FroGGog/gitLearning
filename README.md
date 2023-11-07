# GitHub
---
I'm learning git and github right now, and this is my training task.

## 1 Getting to know GitHub

GitHub is a platform for storing IT projects and collaborating on them using Git. In fact, this is a site where you can upload your project <br>
files for sharing with other people. Indeed, GitHub has become the most popular site for storing Git repositories. Many large companies, such as Google, Apple, Valve, use GitHub for their projects. <br>
1. GitHub is a platform that works with Git and simplifies team interaction.
2. In addition to GitHub, there are other similar platforms, such as Github, Bitbucket, and so on.
3. Git is a console tool for working with local and remote repositories. It is not directly linked to any of the platforms and develops separately from them.

### 1.1 What is SSH. Generating an SSH key

One of the most common network protocols is SSH (Secure Shell Protocol). It provides secure data exchange on the network. Using this protocol, you can receive data from a remote computer or send it to it. The   traffic is encrypted, so the protocol is secure.  
SSH uses a key pair for security public and private:
* The private key is stored only on your computer and should not be transferred to anyone else. It is used to decrypt data.
* The public key is accessible to everyone and is used to encrypt data. They can be decrypted with a paired private key.
Only you can decrypt the data using a private key, but any owner of a public key can encrypt it for you. These two   keys are linked and form an SSH pair. In the future, you will probably use them to interact with GitHub and other   remote servers.

### 1.2 Bind a remote repository to a local one git remote add

git remote add origin %LinkToYourGitRep%   
Origin ("source") is a standard alias with which you can access the main remote repository (usually there is one   
such repository). This greatly simplifies the work.  
Flag -v is the short form of the flag --verbose ("detailed"). It allows you to show more information in the output.  

### 1.3 Synchronizes local and remote repositories

#### Main branch  
We mentioned that each commit keeps the files up-to-date. The comments themselves are stored in branches.  
If a commit is a snapshot of the status of files, then the branch is the timeline on which these snapshots are located. The branch always starts from one of the commits. There may be several branches in the   repository at once parallel change histories. They can also connect to each other.  
Send changes to a remote repository git push  
You have already gone through the entire "commit cycle": prepared the files using git add, committed them with a comment with the git commit -m command. It remains to upload the contents of the local repository to   GitHub. The git push command is responsible for this.  
For the first time, this command must be called with the -u flag and the parameters origin (the name of the remote repository) and main or master (the name of the current branch). The -u flag will link the local   branch with the remote branch of the same name

### 1.4 File README.md
In order for other users, as well as potential clients or employers, to understand what the project is, it needs to be described. It is customary to specify such a description in the file README.md   
As a rule, in README.md you can find the following information about the project:
* The name of the project and its brief description: the cream was created for what, which solves the tasks and which closes the problems.
* Technologies that are used in the project. What is its difference from similar ones.
* Project documentation detailed instructions on what the project is.
* Project plans, if any.
#### How to create and issue README.md  

README.md a text file that can be created with the touch command and then edited in the same way as any other text document. For example, in notepad.  
Advantage README.md the fact is that team work tools (such as GitHub) can display its contents in the browser in the form of convenient markup. To do this, you need to not just fill in the text, but also  
adjust the font, headers and margins using markdown. Markdown is a special markup language. It allows you to format a text document beautifully.  


### 1.5 What is a hash. Hashing commits

Hashing ( "hack", "crumble", "hash") is a way to transform a set of data and get their "fingerprint".  
Commit information is a set of data: when the commit was made, the contents of the files in the repository at the time of the commit and a link to the previous, or parent, commit.  
Git hashes (converts) commit information using the SHA-1 algorithm (from the English Secure Hash Algorithm "secure hashing algorithm") and receives for each commit its own unique hash result of hashing.  
Usually a hash is a short (40 characters in the case of SHA 1) string, which consists of the digits 0-9 and the Latin letters A to F (it does not matter whether uppercase or lowercase). It has the following   important properties:  
* if the hash is obtained twice for the same set of input data, the result is guaranteed to be the same;
* if at least something in the source data changes (at least one character), then the hash will also change (and greatly).
Git stores a table of matches hash → commit information. If you know the hash, you can find out everything else: the author and date of the commit and the contents of the committed files. We can say that the  
hash is the main identifier of the commit.  

### 1.6 File statuses in Git

Untracked/tracked, staged and modified statuses  
One of the key tasks of Git is to track changes to files in the repository. To do this, each file is marked with a status. Let's consider the main ones.  
1. __untracked__: We said that new files in the Git repository are marked as untracked, that is, untraceable. Git "sees" that such a file exists, but does not monitor changes in it. The untracked file has no previous versions fixed in the comments or via the git add command.
2. __staged__ (_"prepared"_) After executing the git add command, the file gets into the staging area (from the English stage — "stage", "stage [of the process]" and area — "area"), that is, in the list of files that will be included in the commit. At this moment, the file is in the staged state.
3. __tracked__: The tracked state is the opposite of untracked. It is quite broad in meaning: it includes files that have already been committed using git commit, as well as files that have been added to the staging area by the git add command. That is, all files in which Git tracks changes in one way or another.
4. __modified__: The modified state means that Git compared the contents of the file with the last saved version and found differences. For example, the file was compromised and then changed.

```mermaid
graph LR;
    A(Untracked)-->|git add| B(Staged);
    B(Staged)-->|git commit| C(Tracked);
    C(Tracked)-->|changes| D(Modified);
    D(Modified)-->|git add| B(Staged);
    B(Staged)-->|changes| D(Modified)
