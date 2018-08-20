## Configure Your Local Environment   

git config --system
These are system-wide configurations. They apply to all users on this computer.    
git config --global
These are the user-level configurations. They only apply to your user account.     
git config--local 
These are the repository-level configurations. They only apply to the specific repository where they are set. The default value for git config is --local.       
     
Git adds several configurations automatically—type git config --list to see config settings from all three levels.     
git config --global user.name "First Last"    
git config --global user.email "you@email.com"    
or to just for that local repository    
git config --local user.name "First Last"     
git config --local user.email "____@____.com"    
git config --local user.password "_____"    

## Configure autocrlf 
Next, we set core.autocrlf (autocrlf stands for auto carriage return line feed). Different systems handle line endings and line breaks differently. If you open a file created on another operating system and do not have this config option set, Git will think you made changes to the file based on the way your operating system handles the line endings.   

For Windows users enter:   
$ git config --global core.autocrlf true   

For Mac or Linux users enter:    
$ git config --global core.autocrlf input   

## Branching    
Step 1: Create a Branch   
To see a list of local branches, type git branch. Right now, you probably only see one branch: master.    

Let’s create a new branch (myfeaturebranch) for our work:   

Type git branch myfeaturebranch   
Checkout to that branch: git checkout myfeaturebranch     

## Adding and committing    
Check the status of our working tree: git status   
Move the file from the working tree to the staging area: git add README.md   
or git add -A     
git commit -m “My first commit”     

## Send Changes to the Remote Repository    
Sending and creating the branch:    
git push -u origin myfeaturebranch   

## Explore history with Git    
git log -10 will only show the 10 most recent commits.    
git log --oneline is a great way to view commit history by displaying the first seven characters of the SHA-1 hash and commit message of the commits on the current branch.     
git log --oneline --graph presents commit history in a ASCII graph displaying the different branches in the repository and their commits.     
git log --oneline --graph --decorate displays the same ASCII graph that is displayed using the --graph modifier, but also includes the branch name(s) for the different commits being displayed.     

You can also use git diff to compare between any two commits, branches, or tags in the repository. For example, to compare two commits with SHA-1 hash references 4e3dc9b and 0cd75d4, enter command: git diff 4e3dc9b 0cd75d4    

Finally, if you would like to view the changes that were made in a previous commit, you can use the git show <SHA-1> command to display the details of that specific commit. It includes things like commit author, time and date of the commit, and a list of the changes that were made to the various assets within the repository.    

## Undoing Changes    
git revert creates a new commit with changes that are the opposite of the commit that is functionally being 'undone'.    

## Git reset    
Git has a git reset command that can help rewind the history of our project, but, it alters the commit history, which as mentioned before, might cause issues for other collaborators. It is highly recommended that you use git reset only when you have not pushed your commits to your remote branch. git reset comes in three distinct flavors, --soft, --mixed, and --hard.    
 
git reset --soft takes the identified commit(s) and places all of the changes in the staging area. This is helpful if you want to take a group of commits and squash them into a single larger commit.     
git reset --mixed, the default mode for git reset, takes the identified commit(s) and places all of the changes in the working directory. Like --soft, this is helpful if you want to take a group of small commits and combine some of the changes to make larger commits. But you can also use it to make additional changes to the files and then re-create the commit history.    
git reset --hard will take the identified commit(s) and destroy them. Be careful with this, because they don’t go in your trash or recycle bin—the files essentially don't exist and are completely removed from your repository. Any uncommitted changes to files that are currently in the working directory or staging area will also be deleted. You can lose work with git reset --hard.     
An example of using reset could look something like this:   
git reset --soft HEAD~2 would rewind the branch you are on by two commits (remember HEAD is a pointer to the tip of your branch). The changes that had been made in those last two commits would be reflected in the staging area    
