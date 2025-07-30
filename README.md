# hello-world
This repository is for practicing the GitHub flow.
Hello! I am Ishta and I am 24 years old. I am looking for a roommate and want to hear back from someone.

To clone a repository: 
1. On GitHub, navigate to the main page of the repository
2. Above the list of files, click <> Code
3. To clone the repository with HTTPS, click the clipboard symbol under HTTPS. To clone the repository with an SSH key, click SSH and then click the clipboard symbol. To clone a repository using GitHub CLI, click GitHub CLI and then click the double square symbol
4. Open terminal
5. Change the current working directory to the location where you want the cloned directory
6. Type git clone, then paste the URL you copied earlier
7. Press enter to create the local clone

To clone an empty repository
1. Navigate to the main page of the repository
2. Click the double square sign in both HTTPS and SSH, or set up in desktop to set it up in the desktop
3. Open terminal
4. Change the current working directory to the location where you want the cloned directory
5. Type git clone and paste the copied URL
6. Press enter to create the local clone

What is Forking?
A new repository that shares code and visibility settings with the original "upstream" repository. Are often used to iterate on ideas or changes before they are proposed back to the upstream repository, such as in open source projects or when a user does not have write access to the upsrtream repository (or proposing changes, using someone else's project as a starting point for your own idea). The permissions and visibility of forks depend on whether or not the upstream repository is public or private, or whether it is owned by an organization
Sync the fork of a repository to keep it up to date with the upstream repository
click on sync fork
From web UI: 
1. Navigate to the main page of the forked repository on GitHub
2. Select Sync Fork dropdown menu
3. Review the details about the commits from the upstream repository and then click Update branch


From GitHub CLI: 
1. use the code gh repo sync owner/cli-fork -b BRANCH-NAME

Syncing a fork branch from the command line
First: configure a remote workplace that will configure to the upstream repository in git
1. Open terminal
2. List the current configured remote repository for the fork (git remote -v)
3. Specify a new remote upstream repository that will be synced with the fork (git remote add upstream [link to repository])
4. verify upstream repository with (git remote -v)
5. Then open the terminal
6. Change the current working directory to the local project
7. Fetch the branches and their respective commits from the upstream repository. Commits to the BRANCH-NAME will be stored in the local branch upstream/BRANCH-NAME (use the command git fetch upstream)
8. check the fork's local branch w/ git checkout main
9. git merge upstream/default branch into the remote default branch

GitHub CLI brings GITHUB to an individual's computer/terminal so they can do all their work in one place, does not require a browser like og github


Create a pull request from a fork: 
hint. if the pull request compares the topic branch with a branch in the upstream repository as the base branch, then the topic branch is called the compare branch or pull request
1. 
