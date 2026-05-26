# create project
mkdir ta23blearngit
cd ta23blearngit

# initialize git repo
git init

# first commit
printf "# LearnGit\n" > readme.md
git add readme.md
git commit -m "Add readme"

# second commit
printf "change 1\n" >> readme.md
git add readme.md
git commit -m "Add change 1 line"

# third commit
printf "feature 1\n" >> readme.md
git add readme.md
git commit -m "Add feature 1 line"

# create feature branch
git switch -c feature

# commit on feature branch
printf "feature 2\n" >> readme.md
git add readme.md
git commit -m "Add feature 2 line"

# switch back to main
git switch main

# commit on main
printf "change 2 (main)\n" >> readme.md
git add readme.md
git commit -m "Add change 2 line on main"

# switch to feature branch
git switch feature

# another feature commit
printf "feature 3 (feature)\n" >> readme.md
git add readme.md
git commit -m "Add feature 3 line on feature"

# merge feature into main
git switch main
git merge feature

# if merge conflict appears, replace readme.md contents with:
printf "# LearnGit\nchange 1\nfeature 1\nfeature 2\nchange 2 (main)\nfeature 3 (feature)\n" > readme.md

# finish merge
git add readme.md
git commit -m "Merge branch 'feature'"

# create tag
git tag -a v0.1.0 -m "First release"

# inspect repo
git log --all --oneline --decorate --graph
git branch
git tag

# add github remote
git remote add origin https://github.com/FL14004/ta23blearngit.git

# push everything
git push -u origin main
git push -u origin feature
git push origin v0.1.0