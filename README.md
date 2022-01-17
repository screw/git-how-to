# git-how-to
Git how-to, tips and tricks

#find the commom ancester of two branches

`git merge-base screw-inet/topic/dmpr-ci-test  topic/dmpr-ci-test-rewrite`

#push "empty"- init branch (dmpr-ci-test-rewrite) in remote 'screw-inet' with the common ancestor (see above) 

`git push -u screw-inet $(git merge-base screw-inet/topic/dmpr-ci-test  topic/dmpr-ci-test-rewrite):refs/heads/topic/dmpr-ci-test-rewrite`


#push all commits one-by-one 

`for rev in $(git rev-list --reverse screw-inet/topic/dmpr-ci-test-rewrite-1..topic/dmpr-ci-test-rewrite);do git push screw-inet $rev:topic/dmpr-ci-test-rewrite-1; done`





To find all commits that added or removed the fixed string whatever. The --all parameter means to start from every branch and --source means to show which of those branches led to finding that commit. It's often useful to add -p to show the patches that each of those commits would introduce as well.

`git log -S <whatever> --source --all`


# rebase on top of specific commit
```
git branch temp <commit>
git checkout topic
git rebase temp
git branch -d temp
```




