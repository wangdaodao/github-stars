---
project: git-sync
stars: 256
description: 🔃 A GitHub Action for syncing between two independent repositories using force push
url: https://github.com/wei/git-sync
---

Git Sync
========

A GitHub Action for syncing between two independent repositories using **force push**.

Features
--------

-   Sync branches between two GitHub repositories
-   Sync branches to/from a remote repository
-   GitHub action can be triggered on a timer or on push
-   To sync with current repository, please checkout Github Repo Sync

Usage
-----

> Always make a full backup of your repo (`git clone --mirror`) before using this action.

### GitHub Actions

# .github/workflows/git-sync.yml

on: push
jobs:
  git-sync:
    runs-on: ubuntu-latest
    steps:
      - name: git-sync
        uses: wei/git-sync@v3
        with:
          source\_repo: "source\_org/repository"
          source\_branch: "main"
          destination\_repo: "destination\_org/repository"
          destination\_branch: "main"
          ssh\_private\_key: ${{ secrets.SSH\_PRIVATE\_KEY }} # optional
          source\_ssh\_private\_key: ${{ secrets.SOURCE\_SSH\_PRIVATE\_KEY }} # optional, will override \`SSH\_PRIVATE\_KEY\`
          destination\_ssh\_private\_key: ${{ secrets.DESTINATION\_SSH\_PRIVATE\_KEY }} # optional, will override \`SSH\_PRIVATE\_KEY\`

##### Using shorthand

You can use GitHub repo shorthand like `username/repository`.

##### Using ssh

> The `ssh_private_key`, or `source_ssh_private_key` and `destination_ssh_private_key` must be supplied if using ssh clone urls.

source\_repo: "git@github.com:username/repository.git"

or

source\_repo: "git@gitlab.com:username/repository.git"

##### Using https

> The `ssh_private_key`, `source_ssh_private_key` and `destination_ssh_private_key` can be omitted if using authenticated https urls.

source\_repo: "https://username:personal\_access\_token@github.com/username/repository.git"

#### Set up deploy keys

> You only need to set up deploy keys if repository is private and ssh clone url is used.

-   Either generate different ssh keys for both source and destination repositories or use the same one for both, leave passphrase empty (note that GitHub deploy keys must be unique for each repository)

$ ssh-keygen -t rsa -b 4096 -C "your\_email@example.com"

-   In GitHub, either:
    
    -   add the unique public keys (`key_name.pub`) to _Repo Settings > Deploy keys_ for each repository respectively and allow write access for the destination repository
    
    or
    
    -   add the single public key (`key_name.pub`) to _Personal Settings > SSH keys_
-   Add the private key(s) to _Repo > Settings > Secrets_ for the repository containing the action (`SSH_PRIVATE_KEY`, or `SOURCE_SSH_PRIVATE_KEY` and `DESTINATION_SSH_PRIVATE_KEY`)
    

#### Advanced: Sync all branches

To Sync all branches from source to destination, use `source_branch: "refs/remotes/source/*"` and `destination_branch: "refs/heads/*"`. But be careful, branches with the same name including `master` will be overwritten.

source\_branch: "refs/remotes/source/\*"
destination\_branch: "refs/heads/\*"

#### Advanced: Sync all tags

To Sync all tags from source to destination, use `source_branch: "refs/tags/*"` and `destination_branch: "refs/tags/*"`. But be careful, tags with the same name will be overwritten.

source\_branch: "refs/tags/\*"
destination\_branch: "refs/tags/\*"

### Docker

$ docker run --rm -e "SSH\_PRIVATE\_KEY=$(cat ~/.ssh/id\_rsa)" $(docker build -q .) \\
  $SOURCE\_REPO $SOURCE\_BRANCH $DESTINATION\_REPO $DESTINATION\_BRANCH

Author
------

Wei He _github@weispot.com_

License
-------

MIT
