# Configurate VPC - CI/CD

## Create VPS user
--> TODO

##  SSH Configuration

Locally, generate ssh key pair.
```bash
ssh-keygen 
```

Add in the configuration file `~/.ssh/config` so the connection can be established by doing `ssh HOST_NAME`
```bash
Host HOST_NAME
  AddKeysToAgent yes
  UseKeychain yes
  HostName HOST (xxx.xxx.xxx.xxx)
  Port PORT (22)
  User USER (root)
  IdentityFile ~/.ssh/KEY_NAME
```

Add key to the ssh agent, and passphrase to the keychain (-K)
```
ssh-add -K ~/.ssh/KEY_NAME
```

Add the public key to the VPS. The following file will be created `~/.ssh/authorized_keys`<br>

```
ssh-copy-id -i ~/.ssh/PUBLIC_KEY USER@HOST -p PORT
```

It may be needed to reboot the ssh daemon in the VPS
```
systemctl restart sshd
```
