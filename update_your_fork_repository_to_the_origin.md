# Update your fork repository to the origin

After you fork a repository, the repository is unrelated to the origin one.
To keep in accordance with the origin, you can use `git remote`.

Make sure you have installed [git](https://git-scm.com/) in your computer. 
Then let's start with [Spoon Knife](https://github.com/octocat/Spoon-Knife.md) as example.

1. fork the repository
2. clone the repository you have forked to your computer
```bash
git clone git@github.com:<Username>/Spoon-Knife.git
```
3. add the origin address using `git remote`
```bash
git remote add upstream git@github.com:octocat/Spoon-Knife.git
```
4. sync the repository to the origin 
    1. go to the directory of the repository.
    2. `git fetch upstream` to check the update of upstream.
    3. `git checkout master` to switch to master.
    4. `git merge upstream/master` to merge the master and the upstream/master.
    5. `git push -u origin` to push to the forked repository.
