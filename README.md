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
2. Select "Sync Fork" dropdown menu
3. Review the details about the commits from the upstream repository and then click "Update branch"


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
   c. TO create a repository from a tempplate, nagivate to the main page of the repository, click use this template above the file list, and select create a new repository, select the account you want to own the repository and name it, choose its visibility or select Include all branches, or any apps to use. Then click on "Create Repository from Template".
3. If you want to include the directory structure and files from all branches in the template, select "Include all Branches"
4. Use the "Owner" dropdown menu to select the account you want to own the repository, type a name for the repository and then choose its visiblity
5. Can create a README, whihc is a document describing the project or a .gitignore file, which is a set of ignore rules (which files and directories to ignore when you make a commit, create it with the "touch .gitignore" command, or to ignore a file that is already checked in, use "git rm --cached FILENAME"). You can also ignore a certain file or directory by adding it to a certain file named ignore inside the directory ~/.config/git, or open the file called .git/info/exclude
6. Select apps to be used in the repository
7. Click "Create Repository"
8. Then at the bottom of the resulting Quick Setup page, under "Import from an old repository", choose to import a project to the new repository by clicking "Import code"

Create a new repository from a URL query
- name = name w/ spaces replaced w/ + or %20
- descripton = string w/ spaces replaced with + or %20
- visibility=private or visibility=public
- owner=name of organization or username or (@me if signed in)
- specify who owns the template and the name of the template with template_owner and template_name

Deleting a repository:
1. On GitHub, navigate to the main page of the repository
2. Under the repository name, click on the settings button. then select the dropdown menu and then click settings
3. On the "General" settings page, scroll down to the "Danger zone" and click "Delete this repository"
4. Read the warnings and click "I have read and understand these effects"
5. Read the warnings and click "I have read and understand these effects"
6. Type in the name of the repository you want to delete in the text box
7. Click "Delete this repository"

Restoring a deleted Repository:
1. In the upper-right corner of any page on GitHub, click the profile picture and then click on "Settings"
2. In the "Code planning and automation" section of the sidebar, click on "Repositories"
3. Then click on "Deleted Repositories"
4. then click "Restore" next to the repository you want to restore
5. Read the warning and then click "I understand, restore this repository"

To add new files to the project's repository:
1. TO the right of the page, select the "Add file" dropdown menu
2. From the dropdown menu, click "Upload files"
3. On the computer, open the folder with all the work, and then drag and drop all files and folders into the browser
4. At the bottom of the page, under "Commit changes", select "Commit directly to the main branch", and then click "Commit changes"

Adding locally hosted code to GitHub:
Initialize a Git repository with: 
1. Open the terminal
2. Navigate to the root directory of the project
3. Initialize the local directory as a Git repository (git init -b to set the name of the default branch)
4. git add . to add the files in the new local repository
5. Commit the files that have been staged in the local repository
Then push the repository to github
CLI: gh repo create, then select "push an existing local repository to github" and enter the desired name. Follow the interactive prompts and then confirm yes when asked to add the remote and push the commits to the current branch
Git:
1. Create a new repository on GitHub
2. Click the double sqaures logo on the Quick Setup page to copy the remote repository URL
3. Open Terminal
4. Change the current working directory to the local project
5. git remote add origin (full URL of the repository in github)
6. run git remote -v to ensure that the remote URL was set correctly
7. git push -u origin main to push the changes in the local repository to GitHub

Creating and Pushing an R-Markdown Document to GitHub (including graphs)
1. Go to github
2. Create new repository (don't need to initialize with the readme, whihc can be added later)
3. Go to R studio > file > new project > version control > Git
4. Ctrl+V repository URL from GitHub, File > New > Markdown> enter title, etc
5. change output = html_document to output = github_document
6. Knit the file, it will have saved as Title.rproj, Title.rmd, Title.md if saved as Title.md
7. Allows the code to be rendered when pushed as igt
8. Check the box to stagre Title.md, not .rmd, click "commit", add comment, click the green arrow to push to GitHub, go to gitHub, refresh the repository, and the markdown document with rendered code will be there

If the document includes graphs: 
when knitted, a new file will save to the Git window called title.docs
When you commit, check the box to stage the .docs in addition to the .md document, which will commit the graphs as a separate file to the repository, although the graphics will automatically pull into the markdown document when rendered
