# No Password When pushing to Your own Github
:vim:

When I pushing my code to github, it failed and asking for password.

## Causing
This will happen only if using **http** link when cloning.

## Solving
Using ssh links which begin with `git@github.com` instead.

### How to change HTTP to ssh
1. show the clone address
```bash
git remote -v
```
2. remove the HTTP link
```bash
git remote rm origin
```
3. add a ssh link
```bash
git remote add origin git@github.com:<Username>/<repository>.git
```

