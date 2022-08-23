I do not claim that the comments after the commands are 100% accurate.
I also do not claim that this is the only way of running such commands.

# Tmux
- tmux ls => List all sessions
- tmux new -s <session_name> => Create new session with name <session_name>
- tmux attach -t <session_name> => Attach to session with name <session_name>
- Ctrl+b + " => Split screen horizontally
- Ctrl+b + % => Split screen vertically
- Ctrl+b + x => Close pane
- Ctrl+b + o => Navigate to other panes
- Ctrl+b + d => Dettach session

# Git
- git init => Initiates Git repository
- git add <file> => Add file to the staging area
- git commit => Commit the contents of the staging area
- git log => Check the history of the commits
- git status => Check the current status of the repository
- git checkout <branch name\|commit id> => Checkout a branch or commit
- git branch => Lists branches in the repository
- git remote add <remote name> <url> => Add remote to repository
- git branch --set-upstream-to=<remote name>/<remote branch> => Link the current branch to a remote branch
- git push => Pushes the local changes to remote
- git fetch => Fetchs changes on the remote
- git merge <branch> => Merge <branch> onto the current branch
- git pull => git fetch && git merge 
- git clone <repo url> => clones remote repository to a local repository
