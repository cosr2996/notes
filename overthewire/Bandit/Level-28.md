# Level-27 -> Level-28

### Level Goat
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.
### Credentials
ssh bandit27@bandit.labs.overthewire.org -p 2220
password: **YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS**
### Solution
```shell
bandit27@bandit:/tmp/secttp$ git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
fatal: could not create work tree dir 'repo': Permission denied
bandit27@bandit:/tmp/secttp$ 


```
### Summary

### FLAG
**flag** 