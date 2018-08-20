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
