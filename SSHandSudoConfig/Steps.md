```bash
  apt update
  apt install openssh-server -y
  nano /etc/ssh/sshd_config
```

Uncomment port
Change port to 1048

Save

```bash
  systemctl enable ssh
```

Ubuntu
```bash
  ssh-keygen -t rsa
  ssh-copy-id {debian username}@{debianIP}
```
