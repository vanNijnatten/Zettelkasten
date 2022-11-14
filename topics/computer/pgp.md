---
tags: 💨 🔖
aliases: 
  - GPG
  - GNU Privacy Guard
  - PGP
  - Pretty Good Privacy
  - OpenPGP
cssclass: idea
publish: true
---
# PGP
See also [[git|Git]] and [[github|GitHub]].

## What is PGP?
Pretty Good Privacy (PGP) is a way to sign messages, to validate the ID of the sender, and to encrypt and decrypt files, messages and emails. It uses symmetric key encryption, and public-key encryption. The GNU Privacy Guard (GPG) is an implementation of the OpenPGP standard (RFC4880) 

I personally use GPG and only to sign commits in [[git|Git]].

## Installation
GPG can easily be installed using the terminal on a **Mac** using  `brew install gnupg`, **Linux** using `sudo apt install gnupg`, or on Windows using the setup executable downloaded from [GPG4Win](https://gpg4win.org/download.html).
Also, on a Mac, install pinentry using `brew install pinentry-mac` and add the line `pinentry-program /usr/local/bin/pinentry-mac` to the file `~/.gnupg/gpg-agent.conf`. The location of pinentry-mac can be determined using `which pinentry-mac`.

## Understanding PGP
See also [this blogpost](https://www.varonis.com/blog/pgp-encryption)

### Scenario 1: validating an identity
This is the type of PGP action that is done by GitHub.
1.

### Scenario 2: sending private emails/messages
1. User A wants to send User B a private email
2. User B generates a public and private key
3. User B keeps the private key and sends back the public key
4. User A encrypts their message using the public key
5. User A sends the private encrypted message
6. User B decrypts the message with the private key

### Scenario 3: encrypting/decrypting files
1. 

## Usage
Create a signing key
```BASH
gpg --full-generate-key
gpg --full-gen-key # Some Linux distros
```

List signing keys
```BASH
gpg --list-secret-keys --keyid-format LONG "9002122+vanNijnatten@users.noreply.github.com"
# sec   rsa4096/2F01902897288144 2021-09-24 [SC] [expires: 2031-09-22]
#       RANDOMNUMBERSANDLETTERSRANDOMNUMBERSANDL
# uid                 [ultimate] Jos van Nijnatten (This is for GitHub only.) 9002122+vanNijnatten@users.noreply.github.com
# ssb   rsa4096/SOMEOTHERIDENTIF 2021-09-24 [E] [expires: 2031-09-22]
# (In this case "2F01902897288144" is the key id.)
```

Export a public key
```Bash
gpg --armor --output gpg_github_pub.asc --export "9002122+vanNijnatten@users.noreply.github.com"
cat gpg_github_pub.asc
# This public key can be added to GitHub via:
# https://github.com/settings/keys
```

Delete a key
```BASH
gpg --delete-secret-key "2F01902897288144"
```

Encrypt a file
```Bash
gpg -r "9002122+vanNijnatten@users.noreply.github.com" -e test.txt
```

Decrypt a file
```Bash
gpg -d test.txt.gpg
```

## Debugging
There is a possibility that when commiting a change in Git, it asks for a password, or nothing at all an just fails. [This Stackoverflow entry](https://stackoverflow.com/questions/41502146/git-gpg-onto-mac-osx-error-gpg-failed-to-sign-the-data) shows how to handle this error. However, you can restart the deamon using `gpgconf --kill gpg-agent` and `gpg-agent --deamon`, perhaps with the `--homedir` option specified.
