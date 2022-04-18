---
tags: ✍️
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
Pretty Good Privacy (PGP is a way to sign messages and to encrypt and decrypt files. The GNU Privacy Guard (GPG) is an implementation of the OpenPGP standard (RFC4880).

## Installation
GPG can easily be installed using the terminal on a **Mac** using  `brew install gnupg`, **Linux** using `sudo apt install gnupg`, or on Windows using the setup executable downloaded from [GPG4Win](https://gpg4win.org/download.html).

## Understanding GPG
See also [this blogpost](https://www.varonis.com/blog/pgp-encryption)

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
