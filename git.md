# Git

## Contents

- [Set Credentials](#set-credentials)
- [Clone Private Repo](#clone-private-repo)
- [Renaming Remote Branch](#renaming-remote-branch)

## Set Credentials

#### Username Password

```bash
# local
git config credential.helper store
# global
git config --global credential.helper store
```

#### SSH key

https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

```bash
git clone git@example.com:root/test.git
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
add key to github/gitlab

---

## Clone Private Repo
```bash
git clone https://username@github.com/username/repository
```

---

## Renaming Remote Branch

```bash
git branch -m new-name
git push origin :old-name new-name
git push origin -u new-name
```
