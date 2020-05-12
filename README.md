# Collection of small usefull bash scripts

Main idea is collectiong small bash scripts that can be usefull in dayly work


## Work with GIT
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
