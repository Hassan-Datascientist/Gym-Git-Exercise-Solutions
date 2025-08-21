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