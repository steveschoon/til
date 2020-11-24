# How To Rebase 

Given this scenario:

1) `master` has the current shipping code
2) `feature/f1` branch has an unrelease feature
3) Some time goes by and fixes happen in `master` while development continues on `feature/f1`

Now it's time to incorporate all the changes from `master` into the feature branch before merging `feature/f1` back to `master`.  

To do this in a terminal:

- `git checkout feature/f1`
- `git rebase master`

To do this in Fork:

- Drag `feature/f1` onto `master` 
- select "Rebase feature/f1 on master"

