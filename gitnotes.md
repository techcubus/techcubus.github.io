#### `git` notes

# remote ssh setup
* Create or find a key
  `ssh-keygen -t ed25519 -C "your_email@example.com"`
* May have to start the agent and add the key
  ` $ evl $(ssh-agent -D)`
  ` $ aah-add ~/.ssh/id_ed25519`
* Add public key to github if necessary under authentication
* Check remote from the repo directory
  ` $ git remote -V`
* Fix if necessary
  `git remote set-url origin git@github.com:USERNAME/REPOSITORY-NAME.git`
* Also test connection
  `$ ssh -T git@github.com`
