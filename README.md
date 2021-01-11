# Description
Grab all repository using Google repo

# HowTo
## Installing repo
First you need the *repo* binary.
```sh
mkdir -p ~/.local/bin
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/.local/bin/repo
chmod a+x ~/.local/bin/repo
```

## Getting the manifest
### Using ssh
```sh
repo init -u ssh://git@github.com/or-tools/repo.git -b main
```
### Using https
```sh
repo init -u https://github.com/or-tools/repo.git
```

note: To change/set your user.name and user.email simply use the option `--config-name`

## Checkout main branch
```sh
repo start --all main
```

## Update/Download all repo
```sh
repo sync -j8
```

Now all is done ...

## Run command
You can easily run a command on each repo e.g.:
```sh
repo forall -c 'echo "$REPO_PROJECT:"; git checkout main'
```

