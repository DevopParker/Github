# Git & Github Crash course:

git config --global user.name "Name" \
git config --global user.email "Email"
- These two commands can setup your git on your local machine
- You can also setup your git config for a single repository by removing the --global flag

After setting up your git config username and email, to remotely clone repositorys via ssh you need an ssh key
- [Githhub Doc to generate SSH Keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

	Step #1:
        - ssh-keygen -t ed25519 -C "your_email@example.com"
        - This command will run through a script to generate an ssh key on your local machine you are currently using.

    Step #2:
	    - Add the SSH public key to your account on GitHub.
        - Settings -> SSH and GPG keys -> New SSH key
        - Copy the entire ssh key including the email to the box provided, and your local machine can now use ssh to clone repositories.

git init
- Create and initialize a git repository (only required once for any given project)
- A repository is a folder used by Git to track all changes of a given project

Working with Commits (Code Snapshots)
Create Commits - a two step process

git add <files(s)>
- staging changes for the next commit

    Examples:
        git add .\index.html
        git add .\index.html .\readme.md
        git add .

git commit
- Create a commit that includes all staged changes, every commit requires a message

    Examples:
        git commit (uses an editor)
        git commit -m "Commit message"

git status
- Check the current changes and branches to be commited

git log
- Chronological list of all the commits on the current project

git checkout <id>
- Allows you to temporarily move to another commit, the other commits that come after the current commit won't be affected.
- HEAD->master points to the current branch that is loaded

Example:\
git checkout a76a0109a88c6c1f59f9af0f0a53bd8f131f7c4d
- This is the inital commit ID of this project

git checkout master 
- moves back to the master branch

git revert <id>
- Reverts to the given commit id, this creates a new commit and doesn't delete the old ones

git reset --hard <id>
- Undo changes by deleting all commits since the <id>

To exclude files from being added and commited to any repository, create a .gitignore file and type the name of the file or folder you want to be excluded from all future add & commits.

# Key Commands to Know:
    git init
    git add <file(s)>
    git commit -m "..."
    git status
    git log
    git checkout <id>
    git revert <id>
    git reset <id>

Understand Git Branches:
As you work on a project you start collecting commits, these commits are organized in branches.
Your first initialization becomes the "master" branch, it is what you see when you run: git log

git branch <name>
- Creates a new branch from the latest commit from the master branch

Further commits on the master branch will not affect the new branch, as well as the new branches commits will not affect the master branch.
This allows teams to work on bug fixes or new features without interfering with eachother.

git merge <name>
- All the commits of the <name> branch will be merged with the commits of the master branch, 
Git will automatically attempt to commit those changes such that nothing is overwritten, if you have     clashing code you may have to manually fix this issue.

git branch
- List all existing branches, the highlighted and branch with the asterisk shows which branch you are currently working on.

git checkout <branch name>
- Git checkout can also be used to switch branches, as well as using a commit <id>

git branch -D <branch name>
- Removes the branch listed

git checkout -b <branch name>
- The -b flag allows you to create and move into the new <branch name>
- You can create a new branch after making changes to master and add them to the new branch as long as you didn't add or commit them to the main.

git merge <branch name>
- Append all commits up to the lastest commit in the <branch name>
- Not all merges require a message, it depends on the conflicts that are resolved.

# Git with GitHub:
Github README.md files use the markup language 
[Github Docs on using Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

git remote

git remote get-url origin

git remote add origin <url of repository> 
- origin will be the name of the local repository but you can use any name.

git push origin master

git push origin <branch name>

git remote set-url origin <https://username@url>
- You can generate a token through GitHub to use as a password for the git remote set-url

git push --set-upstream origin master

git push

- Running the --set-upstream command will allow you to just use 'git push' as an easier method to push your repository to GitHub
- You can also push seperate branches to commit to GitHub and work on them separately
- After merging a branch to the master branch, you can push the merge directly to github without the need to make any add or commits because github will append all of the commits together in the master branch.

git pull
- Fetch from and integrate with another repository or a local branch
- Incorporates changes from a remote repository into the current branch. If the current branch is behind the remote, then by default it will fast-forward the current branch to match the remote
- [Git pull documentation](https://git-scm.com/docs/git-pull)

## Working with repositories that are not your own

git clone <url> <name>
- [Get clone documentation](https://git-scm.com/docs/git-clone)
