# Gym-Git-Exercise-Solutions
## Bundle 1
### Exercise 1 – Git Basics

```bash
mkdir git-exercise
cd git-exercise
git init
echo "My first file" > file1.txt
echo "My second file" > file2.txt
git add .
git commit -m "My initial commit"
git branch -M main
git remote add origin https://github.com/Hassan-Datascientist/git-exercise.git
git push -u origin main
git checkout -b dev
git checkout -b test
git checkout dev
git branch -d test
```

### Exercise 2 – Git Stash and Reset
```bash
cd C:\Users\HP\git-exercise
git status

echo "<h1>Home Page</h1>" > home.html
git add home.html
git stash push -m "home.html changes"
git stash list

echo "<h1>About Page</h1>" > about.html
git add about.html
git stash push -m "about.html changes"
git stash list

echo "<h1>Team Page</h1>" > team.html
git add team.html
git stash push -m "team.html changes"
git stash list

git stash list
git stash pop stash@{1}
git status

git stash pop stash@{2}
git status

git add home.html about.html
git commit -m "Restore home.html and about.html changes"
git push origin main

git stash pop stash@{0}
git status

git reset --hard HEAD
git status

```

#### bundle2

##### Exercise1

```bash
# Create a new branch named ft/bundle-2 and switch to it
git checkout -b ft/bundle-2

# Create a new HTML file and add some content to it
echo "<h1>Our Services</h1>" > services.html

# Stage the new file to be included in the next commit
git add services.html

# Commit the changes with a descriptive message
git commit -m "feat: Add services page"

# Push the new branch to the remote repository and set it as upstream
git push -u origin ft/bundle-2

```
###### Exercise2

# step1

```bash
# Switch to the main branch to create a conflicting change
git checkout main

# Pull the latest changes to ensure the main branch is up to date
git pull origin main

# Create a new branch for the redesign
git checkout -b ft/service-redesign

# Add a specific change to the services.html file
echo "<h1>New and Improved Services</h1>" >> services.html

# Stage and commit the change
git add services.html
git commit -m "feat: redesign services page heading"

# Push the new branch and its changes to the remote
git push -u origin ft/service-redesign

# Switch back to the main branch to create the conflict
git checkout main

# Add a DIFFERENT change to the SAME line in the services.html file
echo "<h1>Service Offerings</h1>" >> services.html

# Stage and commit this second change
git add services.html
git commit -m "fix: quick update to services page"

# Push the changes to the main branch on the remote
git push origin main
```
# step2
```bash

# Switch back to the feature branch to resolve the conflict
git checkout ft/service-redesign

# Merge the main branch into the feature branch. This will cause the conflict.
# (You will then need to manually edit the services.html file to resolve the conflict markers)
git merge main

# After resolving the conflict in the file, stage the changes
git add services.html

# Create a new commit to save the resolution
git commit -m "fix: resolved merge conflict from main"

# Push the final, resolved changes to the remote branch
git push origin ft/service-redesign
```


##### Bundle 3
### Exercise1

```bash
# Create the team page branch
git checkout main
git checkout -b ft/team-page
echo "<h1>Our Team</h1>" > team.html
git add team.html
git commit -m "feat: Add team page"
git push -u origin ft/team-page

# Go back to main and create the contact page branch
git checkout main
git checkout -b ft/contact-page

# Find and cherry-pick the team page commit
git log --oneline ft/team-page
# (Copy the hash you find)
git cherry-pick <team-commit-hash>

# Complete the contact page and push
echo "<h1>Contact Us</h1>" > contact.html
git add contact.html
git commit -m "feat: Add contact page"
git push -u origin ft/contact-page

# Create the faq page branch
git checkout -b ft/faq-page
echo "<h1>FAQs</h1>" > faq.html
git add faq.html
git commit -m "feat: Add faq page"
git push -u origin ft/faq-page

# Revert the cherry-picked commit and push
git revert <team-commit-hash>
git push

```
## Exercise2

```bash
# Create the home page redesign branch
git checkout ft/faq-page
git checkout -b ft/home-page-redesign

# Go to main and make a new commit
git checkout main
echo "body {color: blue;}" > style.css
git add style.css
git commit -m "feat: Add new CSS file"
git push origin main

# Switch back, rebase, and make your final changes
git checkout ft/home-page-redesign
git rebase main
echo "<h1>Welcome to the new homepage!</h1>" > home.html
git add home.html
git commit -m "feat: redesign homepage"
git push -u origin ft/home-page-redesign

```
###### Bundle4
## Exercise1

```bash
# Checkout the main branch
git checkout main

# Create a new file for the exercise
echo "<h1>Hello This is Bundle 4 Exercise</h1>" > home.html
git add home.html
git commit -m "feat: Add home.html for Bundle 4 Exercise 1"

# Push changes to both remotes
git push origin main
git push git-copy main

```
