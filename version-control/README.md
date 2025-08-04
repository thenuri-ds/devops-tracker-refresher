Version Control Basics 

- Clone repository through HTML/SSH

git clone

- Checkout main or specific branch 

git checkout 'branch'

- To create a new branch off of specififced branch 

git checkout -b 'test'

- New branch called tested created. Get to making changes in the codebase 

- Time to see all the files changes

git status 

- Checking only files you have changes have been changed, time to add changes to staging area

git add . - for all 
git add 'file name'

- Changes added to staging area. Time to commit 

git status - can run to check that files are tracked 
git commit -m 'commit message' 

- Push your changes to remote repo

git push 