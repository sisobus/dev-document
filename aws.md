aws
===

### enable password authentification (without pem file)
```bash
  $ sudo vi /etc/ssh/sshd_config
  :%s/PasswordAuthentification\ no/PasswordAuthentification\ yes
```
