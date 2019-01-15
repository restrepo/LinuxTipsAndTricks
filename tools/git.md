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
