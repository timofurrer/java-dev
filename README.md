# java-dev

Just a small virtual box setup containing an Ubuntu 16.04 installation with Java
and Eclipse pre-installed.

I'll only use this machine for some exercises at HSLU. With that I do not have to install Java
on my machine. Yeay! :tada:

## Setup

```bash
vagrant plugin install vagrant-vbguest
vagrant up --provision
vagrant reload  # we have to provision first in order to mount the sync folder
vagrant ssh

# on first launch eclipse installer:
/opt/eclipse/eclipse-inst

# launch eclipse and learn to live with it!
eclpise
```

Login with username *batman* and password *bruce*.
