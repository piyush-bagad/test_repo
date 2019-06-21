# Test Repository: Getting started with GitHub

This is a test repo to get started with GitHub. This also contains some of the git commands I would be using quite regularly.
I will be using this to test anything I would want to test before actually applying it to org repo(s). I have cited relevant sources wherever required, but the main reference has been this awesome (long) [video tutorial][3].

## Frequently used commands

* `git init`: Initializing your local directory as a git repository 
	* Usage: `git init` inside your local directory in the terminal.
	* Comment(s) : Adds a `.git` folder inside the directory. This keeps entire track of your repo.
* `git add` and `git rm`: Adding/removing the given files to/from the _staging area_. 
	* Usage: 
		1. `git add file.txt` adds `file.txt` to the staging area.
		2. `git add *` adds all the untracked/changed files.
		3. `git add -u .`: Adds all the changes made to only the _tracked_ files to the staging area.
		4. `git rm -f file.txt` removes the file from staging area as well as deletes it from your local directory.
		5. `git rm --cached file.txt`: Removes the `file.txt` from the staging area. The local file remains intact.
* `git config`: Before you commit (snapshot) your tracked files from the `staged_area`, you need to configure yourself as a git user.
				This is to make yourself recognizable to GitHub. 
	* Usage:
		1. `git config --global user.email "piyush@wadhwaniai.org"`
		2. `git config --global user.name "Piyush Bagad"`
	* Comment: Using `--global` flag will save this as your account's default identity. Omit `--global` flag to set the identity only in this repository.
* `git commit`: Creates and saves a snapshot of the entire repository.
	* Usage: `git commit -m "Add a name to this commit."`
		1. `git commit --amend`: In case you have modified some of the files after committing and now you want to add those modifications to the same commit with a modified message. Using the previous command will open the previous message in interactive mode that you can edit. You can use `git commit --amend -m "Modified message"` to directly instruct it to modify the message. You can use `git commit --amend --no-edit` for amending without changing the commit message.
	* Comment(s): Use `git commit --help` to see documentation. You should definitely look at the documentation given [here][1].
* `git checkout`: Make the HEAD point to a particular previous commit. It is like temporarily going back in time when you had made a specific commit.
	* Usage:
		1. `git checkout commit_id`: Sets your HEAD to the commit `commit_id`, _i.e._ it will take your repo to that stage while you had committed `commit_id`.
		2. If you want to experiment around with commit `commit_id`, you can do so. When that is done, if you want to revert back to the `master` branch, use `git checkout master`.
		3. `git checkout` can be used with branches, but that is a bit more complex and skipped for now.
* `git revert`: Quits the current commit and creates a new commit which is an exact copy of the previous commit.
	* Usage:
		1. `git checkout commit_curr`: Quits the current commit `commit_curr` and creates a new commit, say `commit_new`, which is an exact copy of the previous commit `commit_prev`.
* `git reset`: Resets and sets up HEAD to one of the previous commits.
	* Usage:
		1. `git reset --hard commit_old`: Throws away all the commits between `commit_curr` and `commit_old` and sets the HEAD to point to `commit_old`. This current branch will get updated to end on `commit_old` instead of `commit_curr`.

### Useful resources/links
1. [Exhaustive documentation](https://devdocs.io/git/)
2. [Some common mistakes and solutions](https://about.gitlab.com/2018/08/08/git-happens/) 


[1]: https://devdocs.io/git/
[2]: https://about.gitlab.com/2018/08/08/git-happens/
[3]: https://www.youtube.com/watch?v=o1nHIbRLMHQ
