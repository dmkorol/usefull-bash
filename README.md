# Collection of small usefull bash scripts

Main idea is collectiong small bash scripts that can be usefull in dayly work


# GIT
### Remove local branches
Remove all local branches except `develop`, `master`, `release`
```
git branch | grep -ve "develop\|master\|release" | xargs git branch -D
```

### Remove remote branches
Remove all remote branches from `origin`, except `develop`, `master`, `release`
```
git branch -r| grep -ve "[^-]develop\|master\|release" | sed 's/origin\///g' | xargs git push origin --force --delete 
```

### Move files/folders with saving history
```
# Create destination folder recursively
mkdir -p libs/static

# Move folders and files except 'libs' folder
ls | grep -v "libs" | xargs -L1 -I{} git mv {} libs/static/
```

### Merge files from other repo
```
git remote add static -f git@github.com/repo-to-merge.git
git merge static/master --allow-unrelated-histories
git commit -am "Merge files from repo-to-merge"
git remote remove static
git push origin master
```

# Folders

### Remove folder fast
Remove `node_modules` without put into the Trash folder and without confirmations
```
rm -rf node_modules 
```

# Network

### Show open ports and what program is using them
```
netstat -lptn
```
```
netstat --tcp --listening --programs --numeric
```

## Fether Reading
https://www.usenix.org/sites/default/files/conference/protected-files/lisa19_maheshwari.pdf
