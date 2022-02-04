# Github Action that pushes to git

This GitHub CI runner image allows to deploy a GitHub project to a remote Git repo.

## How to use

Create a ```main.yml``` :

```
on:
 push:
  branches:
   - main
jobs:
 deploy_to_server:
  runs-on: ubuntu-latetest
  name: Deploy main
  steps:
   - name: Run Script
     uses: actions/github-ci-git-push@v1
     with:
      ssh-input: 'dokku@dokku.me:myapp'
```

Go to GitHub > Project > Settings > Secrets > Actions secrets and add a Variable ```SSH_PRIVATE_KEY``` :

```
-----BEGIN RSA PRIVATE KEY-----
...
-----END RSA PRIVATE KEY-----
```
