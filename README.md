### Git cheat-sheet

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
- 
### Cloning

- clone repository from GitHub to a folder in PWD `git clone <URL> folder_name`

### Ignoring files

- create a git-ignore file in PWD `touch .gitignore`
- open *.gitignore* and add the new ignored file name `cat > .gitignore` → `ignored_file1_name`  → <kbd>Ctrl</kbd> + <kbd>D</kbd>
    - to ignore all the extension, append `*.<extension_name>`  (e.g., `*.log` ) in *.gitignore*
    - to ignore the directory, append `dir_name/` in *.gitignore*
    - ignore tracked file `git rm —cached ignored_file_name` (do not delete the file from working tree)
    
- add *.gitignore*  to the staging area `git add .gitignore`
- Again re-track the file, manually delete the file_name from *.gitignore*

### The staging area comparison

- compare PWD with staging area `git diff file_name`
- compare the last commit with the staging area `git diff -staged file_name`

### File modification

- delete file `git rm file_name`
- rename file `git mv file_name renamed_file_name`
- unstage file `git restore --staged file_name`
- restore file `git checkout -- file_name`
- restore all files `git checkout -f`

### Commits modification

- output commits `git log` (`-p` for viewing diff, `-<n>` for last n commits )
- output all commits `git log --preety=oneline` (`--preety=short` or `--pretty=full` or `==preety=format:<type_formats>` [format_help](https://git-scm.com/docs/pretty-formats))
- commits history `git log --since=<n>.days`(or `.weeks` or `.months`)
- merge all commits & change commit message `git commit -amend` (it will open a vim editor)

### Remote repositories

- output remote repository `git remote` (`-v` for fetch & push url)
- add github repository url as origin `git remote add origin git@github.com:pritishkarmakar17/<folder_name>`
- push pwd to github repository `git push -u origin branch_name` (`:new_branch_name` for pushing naming new_branch_name)
>If it shows `error` or `fatal` then follow following steps:
>- generate a ssh key `ssh-keygen -t ed25519 -C "your_email@example.com"`
>- start the ssh-agent in the background `eval "$(ssh-agent -s)"`
>- add SSH private key to the ssh-agent `ssh-add ~/.ssh/id_ed25519`
>- output of SSH public key `cat ~/.ssh/id_ed25519.pub`
>- add a new SSH key to GitHub account [here](https://github.com/settings/keys)
>- for further [Help](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)
- delete branch in github `git push -d origin bugfix`
- 

### Branch management

- add and switch to new branch `git checkout -b new_branch` (`-b` for new branch)
- switch branch `git checkout branch_name`
- output all branches `git branch`(`-v` for last commit of all branches)
- merge the branch in the working branch `git merge branch_name`
- output of already merged branches `git branch --merged`
- output of not merged branches `git branch --no-merged`
- delete branches `git brnch -d branch_name` (gives error if the branch is not merged)
- forcely delete branches `git branch -D branch_name`

