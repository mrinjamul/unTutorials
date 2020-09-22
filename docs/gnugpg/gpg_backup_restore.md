## GPG Guide:

[GPG backup and restore]

### List Secret Keys:

```sh
 gpg --list-secret-keys
 gpg --list-secret-keys --keyid-format LONG
```

### Export public key:

```sh
 gpg --armor --export <key-id>
```

### Git Configure:

```sh
 git config --global user.signingkey "<secret_id>"
 git config --global commit.gpgsign true
```

### Export following into bashrc or zshrc:

```sh
export GPG_TTY=\$(tty)
```

### Backup gpg key:

```sh
 gpg -a --export <user email> > admin-public-gpg-key
 gpg -a --export-secret-keys <user email> > admin-secret-gpg-key
 gpg --export-ownertrust > admin-ownertrust-gpg.txt
```

### Restore gpg key:

```sh
 gpg --import admin-secret-gpg-key
 gpg --import-ownertrust admin-ownertrust-gpg.txt
```

### If `.gnugpg` directory is empty then configure gpg using following command:

```sh
 gpgconf --kill gpg-agent
```
