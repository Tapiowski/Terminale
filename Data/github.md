```shell
ssh-keygen -t ed25519 -C "your_email@example.com"
```
```shell
$ eval "$(ssh-agent -s)"
> Agent pid 59566
```
```shell
ssh-keygen -t ed25519 -C "your_email@example.com"
```
```shell
ssh-keygen -t ed25519-sk -C "YOUR_EMAIL"
```
```shell
cat ~/.ssh/id_ed25519.pub
```
https://ralphjsmit.com/git-custom-ssh-key
```
Host github_ssh_connection
	HostName github.com
	IdentityFile ~/.ssh/id_rsa_custom
```
```
git clone git@github_ssh_connection:user/repo.git your-folder-name 
```
