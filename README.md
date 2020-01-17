# git-how-to
Git how-to, tips and tricks

#find the commom ancester of two branches
git merge-base screw-inet/topic/dmpr-ci-test  topic/dmpr-ci-test-rewrite

#push "empty"- init branch (dmpr-ci-test-rewrite) in remote 'screw-inet' with the common ancestor (see above) 
git push -u screw-inet $(git merge-base screw-inet/topic/dmpr-ci-test  topic/dmpr-ci-test-rewrite):refs/heads/topic/dmpr-ci-test-rewrite


#push all commits one-by-one 
for rev in $(git rev-list --reverse screw-inet/topic/dmpr-ci-test-rewrite-1..topic/dmpr-ci-test-rewrite);do git push screw-inet $rev:topic/dmpr-ci-test-rewrite-1; done




