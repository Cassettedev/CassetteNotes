[[Home]]
[[Cassette]]
[[Wiki]]
[[Blog]]

[[Humanities]]
[[STEM]]
[[Health]]
[[Docs]]
[[Adulting]]

[[C]]
[[Git]]
[[Javascript]]
[[Vim]]

# Git is a Version Control system
Version Control is a method of tracking and managing the development of a given project. Almost always used in the context of software, but the concepts can be applied to many projects unrelated to software development.

Git is the most popular Version Control software used today. It is neigh-essential for any remotely professional software developer, and highly recommended to hobbyists.

There are GUI applications that allow you to use Git, but I like to know how to use the terminal for most things.

### To create a Git repository from scratch:
Open a directroy in a terminal and type:
```
git init
```
This will create a .git directory

Use:
```
git status
```
to show which branch you are on and what changes have been made. This command it used alot.

Once you create or edit a file, type `git status` again to see the changes you have made. Part of it should display:
```
On branch [INSERT BRANCH]

No commits yet

Untracked files:
	file.example01
```

Once you have made all the edits you would like to make, you can "add the files to the staging area". This can be thought of as putting the files in a temporary "box" before they are commited for good.

You might only want to add one or a few files instead of all the files you have edited. To do this, type:
```
git add file.example01
```
to edit individual files, or:
```
git add -A
```
to affect all files that have been modified, the files that will show in `git status`

If you type `git status` again, you should see something like:
```
On branch [INSERT BRANCH]

No commits yet

Changes to be committed:
	new file: file.example01
```

If you type 
```
git rm file.example01
```
you can remove the file. `git status` should display:
```
On branch [INSERT BRANCH]

No commits yet

Chnages to be committed:
	deleted: file.example01
```

You can now commit the file. "Committing a file" can be thought of as taking a snapshot of its current state. To make a commit, type:
```
git commit -m "[INSERT MESSAGE HERE]"
```
The reason for the `-m ""` command is to send a message that is asscosiated with the commit. This message, that you fill into the quotation marks, should breifly explain what the commit does and why it was done. For example, after we made changes to file.example01, the message could be:
```
git commit -m "Created file.example01"
```

### Pushing to Github
Github is not actually a part of Git. Github is a service where you can host your files that you upload through Git.

`git commit` will not actually push your changes to Github. For this, you have to use the "push" command:
```
git push origin [INSERT BRANCH HERE]
```

After this, you will be prompted to enter your username and your "password", though I used a generated token, as It seems to be the only way it works for me.


