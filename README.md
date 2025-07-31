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
The topic branch, aka the feature branch, is the branch where one is making the forked changes
The base branch is the branch in the central repository that you want to make changes into
The pull request compares the changes proposed by the topic branch with the base branch (known as compare branches)
1. Navigate to the original repository where you created the fork
2. Above the list of files, there is a yellow banner. Click compare and pull request to create a request for the associated branch
3. On the page to create a new pull request, click compare across forks
4. In the "base branch" dropdown menu, select the branch of the upstream repository you'd like to merge changes into
5. in the head fork dropdown menu, select your fork, then use the compare branch dropdown menu to slect the branch you made your changes in
6. Type a title and description for your pull request
7. On user-owned forks, select "Allow edits from maintainers" to allow anyone to have push access to the upstream repository
8. To create pull request that is ready for review, create pull request. to create a draft pull request, use the drop-down and select "Create Draft Pull Request", then click "Draft Pull Request". If you are the member of an organization, you may need to request access to pull requests from an organization owner

Allowing changes to an existing pull request branch created from a fork:
1. On Github, navigate to the main page of the upstream repository of the pull request
2. Under the upstream repository name, click Pull Requests
3. In the list of pull requests, navigate to the pull request that you'd like to allow commits on
4. On user-owned forks, if you want to allow anyone with push access to the upstream repository to make changes on the pull request, select allow edits from maintainers or Allow Edits and access to secrets by maintainers

- If you fork a private repository that belongs to a personal account, external collaborators get access to the fork
- If you fork a private repository that belongs to an organization, teams within the organization get access to the fork but the external collaborators do not
- You can add an external collaborator to a fork of a private repository owned by an organization if you are an organization owner, or if the organization allows repository administrators to invite external collaborators, and the external collaborator also has access to the upstream repository
- all forks in the repository network has the same visibility setting (repository network contains upstream repository, its forks, and all the forks of the forks)

What happens to a fork when a repository is deleted or changes visibility:
- All Private forks are deleted when in a private repository
- When the public fork is deleted, the oldest, active public fork is chosen to be the new upstream repository, everything else is forked off this new upstream, subsequent pull requests go to it
- Private forks inherit the permissions structure of the upstream repository and only team permissions are inherited by private forks
- If a public repository is made private, its public forks are split off into a new network (detatched from the original repository) and one of the existing public forks is chosen to be the new upstream repository (remaining public even after the repository becomes private), not possible to restore who was able to see the previously public repository before if it is made public again
- When a private repository is made public, all the commits in that repository are migrated to a new public repository and become visible to everyone (incuding the commits made to private forks) but the previously createdprivate forks will remain private, being dfisconnected to the original repository. They will become a separate private repository of their own (individual ones) and create their own independent networks of repositories
- If a private repository is made public and then deleted, its private forks will continue to exist as standalone private repositories in separate networks

Detaching a fork can be done by leaving the network manually or deleting it and recreating it without any connection to the original fork
Manually leaving the fork network:
1. Open terminal
2. Create a bare clone of the fork with the code git clone --bare [link to fork]
3. delete the forked repository (copies the git version control data without a working directory)
4. Create a new repository with the same name in the same location
5. Mirror-push the repository back to the same emote URL (git --git-dir FORK.git push --mirror [link to fork])
6. Remove the temporary local clone (rm -rf FORK.git)

Creating a repository from a template is similar to forking a repository but with important differences: 
- A new fork includes the entire commit history of the parent repository while a repository created from a template starts with a single commit
- Commits to a fork do not appear in the contributions graph while commits to a repository created from a template do appear in the contribution graph
- A fork can be a temporary way to contribute code to an existing project while creating a repository from a template starts a new project quickly

 A repository contains all the code, files, and each file's revision history (https://github.com/new) to make a new one

Creating a new repository:
From the Web UI:
1. In the upper-right corner of any page, select +, then cluck New Repository
2. Or to create a repository with the directory structure and files of an existing repository, select the choose a template dropdown menu and click a temporate repository (owned by you or organizations you are a member of, or ones you've used before).
   a. To create a template repository, create a repository, then navigate to its main page, then under the repository name click settings (can be found underneath the dropdown menu), and select template repository
   b. You can choose to include the directory structure and files from only the default branch of the template repository or to include all branches. Branches createed from a template have unrelated histories, which means you cannot create pull requests or merge between the branches.
   c. TO create a repository from a tempplate, nagivate to the main page of the repository, click use this template above the file list, and select create a new repository, select the account you want to own the repository and name it, choose its visibility or select Include all branches, or any apps to use. Then click on Create Repository from Template.
3. 

Deleting a repository:
