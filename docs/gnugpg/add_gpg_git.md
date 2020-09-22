## Adding gpg to git

#### Check if a gpg key already exists

```sh
gpg --list-secret-keys --keyid-format LONG
```

#### If not exists, Create a gpg key

[NOTE: you need to have gnugpg installed]

If you are on version 2.1.17 or greater, paste the text below to generate a GPG key pair.

```sh
    gpg --full-generate-key
```

If you are not on version 2.1.17 or greater, the gpg --full-generate-key command doesn't work. Paste the text below and skip to step 6.

```sh
 gpg --default-new-key-algo rsa4096 --gen-key
```

At the prompt, specify the kind of key you want, or press Enter to accept the default RSA and DSA.

Enter the desired key size. Your key must be at least 4096 bits.

Enter the length of time the key should be valid. Press Enter to specify the default selection, indicating that the key doesn't expire.

Verify that your selections are correct.

Enter your user ID information.

Type a secure passphrase. [optional]

#### Read gpg key

Use the `gpg --list-secret-keys --keyid-format LONG` command to list GPG keys for which you have both a public and private key. A private key is required for signing commits or tags.

```sh
gpg --list-secret-keys --keyid-format LONG
```

From the list of GPG keys, copy the GPG key ID you'd like to use. In this example, the GPG key ID is 3AA5C34371567BD2:

    gpg --list-secret-keys --keyid-format LONG
    /Users/hubot/.gnupg/secring.gpg
    ------------------------------------
    sec   4096R/3AA5C34371567BD2 2016-03-10 [expires: 2017-03-10]
    uid                          Hubot
    ssb   4096R/42B317FD4BA89E7A 2016-03-10

Paste the text below, substituting in the GPG key ID you'd like to use. In this example, the GPG key ID is 3AA5C34371567BD2:

```sh
gpg --armor --export 3AA5C34371567BD2
# Prints the GPG key ID, in ASCII armor format
```

Copy your GPG key, beginning with `-----BEGIN PGP PUBLIC KEY BLOCK-----` and ending with `-----END PGP PUBLIC KEY BLOCK-----`.

Add this to any git like services

#### Tell git to use gpg key

To set your GPG signing key in Git, paste the text below, substituting in the GPG key ID you'd like to use. In this example, the GPG key ID is `3AA5C34371567BD2`:

```sh
git config --global user.signingkey 3AA5C34371567BD2
```

To add your GPG key to your bash profile, paste the text below:

```sh
test -r ~/.bash_profile && echo 'export GPG_TTY=$(tty)' >> ~/.bash_profile
echo 'export GPG_TTY=$(tty)' >> ~/.profile
```

[Note: If you don't have .bash_profile, this command adds your GPG key to .profile.]

#### Add email to existing gpg key

Associating an email with your GPG key

Use the gpg --list-secret-keys --keyid-format LONG command to list GPG keys for which you have both a public and private key. A private key is required for signing commits or tags.

```sh
gpg --list-secret-keys --keyid-format LONG
```

Enter gpg --edit-key GPG key ID, substituting in the GPG key ID you'd like to use. In the following example, the GPG key ID is 3AA5C34371567BD2:

```sh
gpg --edit-key 3AA5C34371567BD2
```

Enter gpg> adduid to add the user ID details.

    $ gpg> adduid

Follow the prompts to supply your real name, email address, and any comments. You can modify your entries by choosing N, C, or E. To keep your email address private.

    Real Name: Octocat
    Email address: octocat@github.com
    Comment: GitHub key
    Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit?

Enter O to save your selections.

Enter your key's passphrase.

Enter `gpg --armor --export GPG key ID`, substituting in the GPG key ID you'd like to use. In the following example, the GPG key ID is `3AA5C34371567BD2`:

    $ gpg --armor --export 3AA5C34371567BD2
    # Prints the GPG key, in ASCII armor format
