repo init 
repo sync -c
repo start lb --all
git add -A  （注意与“git add .”的区别）
git commit
repo upload
git stash
git clean –f –d
git rm -rf
git log查看log日志，可以看到很长的一串字符
git reset –hard 长串字符，可以把本地库同步到指定版本
git pull拉取远程改动
