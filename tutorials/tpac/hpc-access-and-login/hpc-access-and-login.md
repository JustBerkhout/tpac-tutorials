---
id: hpc-access-and-login
summary: How to request an account on the TPAC High Performance Computing (HPC) clusters.  How to login through jumpbox.tpac.org.au
categories: hpc
tags: tutorial,ssh,hpc,terminal,account
difficulty: 1
status: draft
published: 2019-05-14

---

# Getting a HPC account and logging in using ssh
Duration: 1:00

## Overview

TPAC have a range of high High Performance Computing (HPC) clusters for various uses.  When you request a HPC account the administrators will talk to you about your project and help you select the right cluster for you.

### What you'll learn
* How to get a HPC account at TPAC
* How to connect using ssh
* How to authenticate

### What you'll need

You'll need to have completed these previous tutorials:
* [chosing-a-terminal-emulator](./tutorials/chosing-a-terminal-emulator)

## Overview of HPC systems
Duration: 3:00

![TPAC HPC Facilities (May 2019)](/images/tpac-hpc-facilities.png)

All systems are provided:
* 100TB of DMF cache
* 70TB of SAS scratch
* 2PB of tape storage
* Interconnectivity via Infiniband fabric

### Requesting an account

Accounts can be requested by completing [this form][get-hpc-account] and submitting it.  If you have an existing account, or are not sure, please submit a help request instead by emailing helpdesk@tpac.org.au.

Once your account is created you will get an email containing further instructions

## How to connect
Duration: 1:00

Access to the clusters uses SSH, so if you're unfamiliar with SSH then you might like to consider the following tutorials:
* [Choosing a Terminal Emulator][chosing-a-terminal-emulator]
* [Using SSH and generating SSH keys][ssh-keygen-linuxes]

Access to Eddy and Kunanyi is via jumpbox.tpac.org.au so you should connect to that first:

```bash
ssh YourAccount@jumpbox.tpac.org.au
```

Once connected to jumpbox please read the “Message of the Day” (MOTD) for cluster status and instructions for how to connect to each cluster, but it might be as simple as:

```bash
ssh kunanyi
```

## What next?
Duration: 1:00
You should definitely consider [learning the command line][command-line-for-beginners], and also spending some time understanding [basic HPC commands][basic-hpc-commands]


<!-- LINKS -->
[get-hpc-account]: https://docs.google.com/forms/d/e/1FAIpQLSeiCUaSSvHHUxfPL1L-sFHqgKqLYeyIf4KBsMpd57QCRxzI9w/viewform?usp=sf_link
[commdocs]: https://help.ubuntu.com/community/SSH/OpenSSH/Keys
[msubuntu]: https://www.microsoft.com/en-us/store/p/ubuntu/9nblggh4msv6
[getstartedcli]: https://help.ubuntu.com/community/UsingTheTerminal
[github]: https://help.github.com/categories/authenticating-to-github/
[launchpad]: https://help.launchpad.net/YourAccount/CreatingAnSSHKeyPair
[azure]: https://docs.microsoft.com/en-us/azure/virtual-machines/linux/ssh-from-windows
[ubuntuonwin]: https://www.microsoft.com/en-us/store/p/ubuntu/9nblggh4msv6
[ubuntuonwintut]: https://tutorials.ubuntu.com/tutorial/tutorial-ubuntu-on-windows
[putty]: http://www.putty.org/
[mobaxterm]: https://mobaxterm.mobatek.net/download.html
[askubuntu]: https://askubuntu.com/
[forums]: https://ubuntuforums.org/
[ubuntuirc]: https://wiki.ubuntu.com/IRC/ChannelList
