repo init 
repo sync -c
repo start lb --all
git add -A  （注意与“git add .”的区别）
git commit
repo upload
