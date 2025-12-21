# `git` notes

## Remote over ssh setup
* Create or find a key
>  `ssh-keygen -t ed25519 -C "your_email@example.com"`
* May have to start the agent and add the key
> ```bash
>  $ eval $(ssh-agent -D)
>  $ aah-add ~/.ssh/id_ed25519
> ```
* Add public key to github if necessary under authentication
* Check remote from the repo directory
>  ` $ git remote -V`
* Fix if necessary
>  `git remote set-url origin git@github.com:USERNAME/REPOSITORY-NAME.git`
* Also test connection
>  `$ ssh -T git@github.com`

* To create a repo on my computer and push to existing github repo,

> ```bash
> $ echo "# DecentSampler-Presets" >> README.md
> $ git init
> $ git add README.md
> $ git commit -m "first commit"
> $ git branch -M main
> $ git remote add origin https://github.com/techcubus/RepoName.git
> $ git push -u origin main
> ```

…or link & push an existing repository 

> ```bash
> $ git remote add origin https://github.com/techcubus/RepoName.git
> $ git branch -M main
> $ git push -u origin main
> ```

On Windows, running in PowerShell, for me this appeared to hang git without an error as a dialog to pick the authentication method had opened behind other windows.
