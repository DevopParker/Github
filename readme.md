#Git & Github Crash course:

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

        Example:
            git checkout a76a0109a88c6c1f59f9af0f0a53bd8f131f7c4d
            - This is the inital commit of this project
            
            git checkout master 
            - moves back to the master branch

    git revert <id>
    - Reverts to the given commit id, this creates a new commit and doesn't delete the old ones

    git reset --hard <id>
    - Undo changes by deleting all commits since the <id>

    To exclude files from being added and commited to any repository, create a .gitignore file and type the name of the file or folder you want to be excluded from all future add & commits.

    #Key Commands to Know:
    git init
    git add <file(s)>
    git commit -m "..."
    git status
    git log
    git checkout <id>
    git revert <id>
    git reset <id>