---
tags: ✍️
aliases: 
  - ssh
  - secure shell protocol
  - secure shell
cssclass: idea
publish: true
---
# SSH
Using the Secure Shell Protocl (SSH) it is possible to connect and authenticate to remote services and servers. For this a public/private keypair needs to be created. The public key is shared with the remote server to decrypt any traffic to it, while the private key is used to encrypt the data and is never shared with anyone.

## Generating keys
For both a SSH connection to a server and for [[git|Git]] over SSH, we need to create a public/private keypair. Depending on the Operating System (OS), this can be done in different ways. Fortunately, this process is always relatively simple.

For **[[Windows]]**, open Git Bash, for **[[Mac]]** and **[[Linux]]** just open the terminal. Execute `ssh-keygen -t rsa -b 4096 -C "9002122+vanNijnatten@users.noreply.github.com"`, and follow the steps in the program. Of course replace "9002122+vanNijnatten@users.noreply.github.com" with your email address. If you use GitHub as a remote branch, the type of email shown above can be obtaind from the [email page](https://github.com/settings/emails).
When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location. Make sure to add an actual key phrase, don't leave it empty!

Before the key can be used, the key must be added to the SSH agent. For this, the agent must be running; run `ssh-agent -s` to make sure it does. Thereafter the newly created private key can be added using `ssh-add ~/.ssh/id_ed25519`, where '~/.ssh/id_ed25519' is the location of the actual private key.
**Mac** users must also edit their '~/.ssh/config' file by adding the following lines:
```BASH
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```
