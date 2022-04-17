---
tags: ✍️
aliases: 
  - GPG
  - PGP
cssclass: idea
publish: true
---
# GPG
## What is GPG?
The GNU Privacy Guard (GPG) is an implementation of OpenPGP.

## Installation
GPG can easily be installed using the terminal on a **Mac** using  `brew install gnupg`, **Linux** using `sudo apt inst all gnupg`, or on Windows using the setup executable downloaded from [GPG4Win](https://gpg4win.org/download.html).

## Understanding GPG

## Usage
Create a signing key
```BASH
gpg --full-generate-key
```

List signing keys
```BASH
gpg --list-secret-keys --keyid-format LONG "9002122+vanNijnatten@users.noreply.github.com"
# sec   rsa4096/2F01902897288144 2021-09-24 [SC] [expires: 2031-09-22]
#       RANDOMNUMBERSANDLETTERSRANDOMNUMBERSANDL
# uid                 [ultimate] Jos van Nijnatten (This is for GitHub only.) 9002122+vanNijnatten@users.noreply.github.com
# ssb   rsa4096/SOMEOTHERIDENTIF 2021-09-24 [E] [expires: 2031-09-22]
# (In this case "2F01902897288144" is the key id.)
gpg --armor --output gpg_github_pub.asc --export "9002122+vanNijnatten@users.noreply.github.com"
cat gpg_github_pub.asc
# Perhaps you also would like to add the public key to GitHub at 
# https://github.com/settings/keys
```

Delete a signing key
```BASH
gpg --delete-secret-key "2F01902897288144"
```
