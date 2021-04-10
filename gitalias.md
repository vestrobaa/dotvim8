# Sanity copy of aliases. Copy to .gitconfig

[alias]

# log listing
ll = log --pretty=oneline -n 20 --graph --abbrev-commit --decorate

# log files that changed
lfiles = log --pretty=oneline -n 20 --graph --abbrev-commit --decorate --numstat

# log file's history
lfile = log -u

# log list a commmit
lc  = "!f() { git ll "$1"^.."$1"; }; f"

# stat short
st = status -s

# diff summary
ds = diff --dirstat=lines --summary

# diff a commit
dc  = "!f() { git diff "$1"^.."$1"; }; f"

# diff index
di = !"git diff-index --quiet HEAD -- || clear; git --no-pager diff --patch-with-stat"

# verbose
aliases = "!git config -l | grep alias | cut -c -50"

# branch done tag
bdone = "!f() { git branch | grep "$1" | cut -c 3- | grep -v done | xargs -I{} git branch -m {} done-{}; }; f"

# commit ammend
ca = commit --amend --reuse-message=HEAD

# list contributors
lcontrib = shortlog --summary --numbered
logp = log --pretty=format:\"%h - %an, %ar : %s\"
