# git branch control

## git branch -a
(result)
master
remotes/origin/branch_name

## git checkout remotes/origin/branch_name


## Error when installing bower package
Additional error details:
fatal: unable to connect to github.com:
github.com[0: 192.30.252.131]: errno=Connection refused

git config --global url."https://".insteadOf git://

## git pull by changeID
git ls-remote | grep 1220

git pull origin refs/changes/20/1220/2
