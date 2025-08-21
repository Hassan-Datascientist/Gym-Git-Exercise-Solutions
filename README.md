# Gym-Git-Exercise-Solutions
## Bundle 1
### Exercise 1 – Git Basics

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


