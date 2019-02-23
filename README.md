# Git Tools
using git on **Windows**

## use ssh to logon github.com

```shell
> cd %userprofile%\.ssh\
> ssh-keygen -t rsa -C "<your-email-address>"

Generating public/private rsa key pair.
Enter file in which to save the key (C:/Users/<your_username>/.ssh/id_rsa): 

> C:\Users\<your_username>\.ssh\id_rsa_<your_username>

> <your_passphrase>
```

Paste *.pub to github.com -> "Settings" -> "SSH and GPG keys".

## setting up multiple github accounts

using VS code as editor

```shell
> cd %userprofile%\.ssh\
> code config
```

config file content:

```txt
# default github account
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa

# other accounts
Host github_<you_name_it>
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_<you_name_it>
```

to clone repository from the other account
```shell
git clone git@github_<you_name_it>:<your_github_account>/<your_github_repo>.git
```

to set username and email for this repo,
after that the change can be seen on the file ".git\config" under your repo folder
```shell
git config user.name "<your_user_name>"
git config user.email "<your_email>"
```