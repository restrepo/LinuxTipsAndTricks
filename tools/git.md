# Git
## Permanently authenticating with Git repositories
Run following command to enable credential caching:
```bash
$ git config credential.helper store
$ git push https://github.com/repo.git

Username for 'https://github.com': <USERNAME>
Password for 'https://USERNAME@github.com': <PASSWORD>
```

See: https://stackoverflow.com/a/28562712

## git checkout for Remote Branches
From: https://www.git-tower.com/learn/git/faq/checkout-remote-branch

The syntax for making git checkout "remote-ready" is rather easy: simply add the `--track` flag and the remote branch's ref like in the following example:
```bash
$ git checkout --track origin/newsletter
```
Based on the remote branch `origin/newsletter`, we now have a new local branch named `newsletter`.

From here on, you can make changes and commit them to your new local branch like you're used to.

## Delete last commit and remove it from remote repository
See https://stackoverflow.com/a/8225166/2268280
```bash
git reset HEAD^ # remove commit locally
git push origin +HEAD # force-push the new HEAD commit
```
