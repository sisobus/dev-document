git
===

### git credential
```
    $ git config --global user.name "Sangkeun Kim"
    $ git config --global user.email "sisobus@vuno.co"
    $ git config --global credential.helper cache (linux)
        $ git config --global credential.helper osxkeychain (linux)
    $ git config --global credential.helper store
```

### git log pretty
```bash
    alias gitlogall='git log --graph --oneline --all'
    alias gitg="git log --graph --all --format=format:'%C(bold blue)%h%C(reset) -- %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(bold white)-- %an%C(reset)%C(bold yellow)%d%C(reset)' --abbrev-commit --date=relative"
```
