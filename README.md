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

## Banching    
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
