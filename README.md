# Git basic command lines
### Git cheat sheet

[git cheatsheet html page](https://ndpsoftware.com/git-cheatsheet.html#loc=remote_repo;)

### Configuration of Git

- set username `git config --global user.name "<user_name>"`
- output username `git config --global user.name`
- set email `git config --global user.email "<email>"`
- output email `git config --global user.email`
- `git config —list`


### Basics of Git project

- make a git repository `git init project_name`
- check status `git status`
- add the file in the staging area `git add file_name` (`-a` for all file)
- commit the stage `git commit -m “<some_command>”` (`-m`  for message)
- output all commits `git commit -a`
- commit all the tracked file `git commit -a -m “<some_command>”`
- remove git repository `rm -rf .git`
### Cloning

- clone repository from GitHub to a folder in PWD `git clone <URL> folder_name`

### Ignoring files

- create a git-ignore file in PWD `touch .gitignore`
- open *.gitignore* and add the new ignored file name `cat > .gitignore` → `ignored_file1_name`  → <kbd>Ctrl</kbd> + <kbd>D</kbd>
    - to ignore all the extension, append `*.<extension_name>`  (e.g., `*.log` ) in *.gitignore*
    - to ignore the directory, append `dir_name/` in *.gitignore*
    - ignore tracked file `git rm —cached ignored_file_name` (do not delete the file from working tree)
    
- add *.gitignore*  to the staging area `git add .gitignore`
- Again re-track the file, manually delete the file_name from .*gitignore*

### The staging area comparison

- compare PWD with staging area `git diff file_name`
- compare the last commit with the staging area `git diff -staged file_name`

### File modification

- delete file `git rm file_name`
- rename file `git mv file_name renamed_file_name`
- unstage file `git restore --staged file_name`
- restore file `git checkout -- file_name`
- restore all files `git checkout -f`
- 

### Commits modification

- output commits `git log` (`-p` for viewing diff, `-<n>` for last n commits )
- output all commits `git log --preety=oneline` (`--preety=short` or `--pretty=full` or `==preety=format:<type_formats>`[format_help](https://git-scm.com/docs/pretty-formats))
- commits history `git log --since=<n>.days`(or `.weeks` or `months`)
- merge all commits & change commit message`git commit -amend` (it will open a vim editor)

### Remote repositories
