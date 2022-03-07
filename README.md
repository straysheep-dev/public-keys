# public-keys

| File                         | Description    |
| ---------------------------- | -------------- |
| `straysheep-dev.gpg.asc`     | Public gpg key |
| `straysheep-dev.ssh-rsa.pub` | Public ssh key |

## ssh

To view an ssh public key from GitHub:
```bash
curl https://api.github.com/users/straysheep-dev/keys
# or from an ubuntu system running openssh-server:
ssh-import-id -o - gh:straysheep-dev
```

To **append** the ssh key to an authorized key file for a user:
```bash
curl -Lf '<github-link-to-public-key>' >> ~/.ssh/authorized_keys
```

## gpg

To review a gpg public key / key file:
```bash
# Note: gpg won't do anything if you don't supply any arguments, 
# allowing you to check the key before importing or using it
curl -LfO '<github-link-to-gpg-key>'
gpg ./straysheep-dev.gpg.asc
```

To import the gpg public key from a file:
```bash
gpg --import ./straysheep-dev.gpg.asc
```

To import the public key from a keyserver:
```bash
gpg --keyid-format long --keyserver hkps://keyserver.ubuntu.com:443 --recv-keys '9906 9EB1 2D40 9EA9 3BD1  E52E B09D 00AE C481 71E0'
```

## to do:
- [ ] Upload the private keys after a [sufficient number of qubits are operational](https://en.wikipedia.org/wiki/Shor%27s_algorithm).
