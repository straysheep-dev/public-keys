# public-keys

| File                         | Description    |
| ---------------------------- | -------------- |
| `straysheep-dev.gpg.asc`     | Public gpg key |
| `straysheep-dev.ssh-rsa.pub` | Public ssh key |

## ssh

```
# public key:
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDQoacgIXs4LQCmc46e7SbbgimNVBPqM8KkDV5NrGpzp8aqYkl21XH+6rKhYhQTX2EzCsJ4UjnsQdvl/lIXk3KXfl6HNrRyyZKQt1omGlsu5QUiFbVtOBC4fx/C8UKBgNli1Ao5qg/+VpfQkJTfKctqwrpG/a42ervwM5tXsrf9KSI5XB/+bWqDIza4ABssTmvgoOW7a9cvXtoFZimh947U6HV+5LLBeUF9A6cU99c16vp/VGrJXCcHoKMRzhk+gXNbr7e9mYvipWU55q+6fv/8SEN3++hm/RKSZCgD38t4ES7DyyJurUSr13eNt8TSdEH1ZBBzTFFMYydEswTahzRRDWwFzkzsXKpC0IYV6+Qo4eoKTkfXpNxayfpA8gziJJzHTNVJgkPfyyuTOXCYgs7JNzw2cz/pq2eQE7bxJxJ3CsQ0JTo477D0MZzyEYJ1KoB6Y6CSQe/UXnyisV3CtIsO7lFP+7yBEoj9uN97BJ4i7BXuOqb2VIBGyd5zbYc4JZfYcp4tVxzWm3L5nAnYahqWETpdiSleTf7fZEofV+4VsQQTNLHMF8aIPCmBrH6EvUwyHRbNBD7B8kTn4XfUZV7Y4W+VtDLLhM0w/8GxbD0HrX3KdTZfnD9W23hQ95/EVUrNk6cV2KhLeYeXMXlZIJ3+LThhaydP7vo2xP4sY3FnzQ==
```

To view an ssh public key from GitHub:
```bash
curl 'https://api.github.com/users/straysheep-dev/keys'
# or from an ubuntu system running openssh-server:
ssh-import-id -o - gh:straysheep-dev
```

To **append** the ssh key to an authorized key file for a user:
```bash
curl -Lf '<github-link-to-public-key>' >> ~/.ssh/authorized_keys
```

## gpg

```
# public key fingerprint:
9906 9EB1 2D40 9EA9 3BD1  E52E B09D 00AE C481 71E0
```

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
