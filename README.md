# GitHub SSH without agent

1. This assumes an SSH keypair exists, usually in ~/.ssh (windows C:\Users\<username>\.ssh). If not, for help creating one see
```
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
```
2. This assumes a git repository exists, otherwise create one as usual `git init`

3. Create a Repository on GitHub

4. Add SSH key to GitHub

5. Add the remote origin from github

```
git remote add origin git@github.com:<username>/<repo>.git
```
6. To verify, use
```
git remote -v
```

7. Edit your SSH config-file `~/.ssh/config` (windows `C:\Users\<username>\.ssh\config`) and add a Host

```
Host github.com
  IdentityFile /my/individual/path/id_rsa
```

8. Edit the git projects config-file `.git\config` and add in [core]

```
sshCommand = "ssh -F <path/to/ssh/config/file>"
```

9. Use git push like usual

```
git push origin master
```
