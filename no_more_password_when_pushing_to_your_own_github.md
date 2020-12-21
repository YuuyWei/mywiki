# No Password When pushing to Your own Github
when I pushing my code to github, it failed and asking for password.

# Causing
This will happen only if using **http** link when cloning.

# Solving
Using ssh link instead.

## How to change http to ssh
1. show the clone address
```bash
git remote -v
```
2. remove the http link
```bash
git remote rm origin
```
3. add a ssh link
```bash
git remote add origin git@github.com:<Username>/<repository>.git
```

