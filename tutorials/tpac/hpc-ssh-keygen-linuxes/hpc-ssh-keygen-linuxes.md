---
id: hpc-ssh-keygen-linuxes
summary: Use appropriate tools to connect to remote computers using SSH.  Generate SSH keys and install SSH keys for better security.
categories: hpc
tags: ssh, keypair, authentication
difficulty: 3
status: published
published: 2019-05-14

---

# Using SSH and generating SSH keys
Duration: 1:00

## Overview

SSH, the secure shell, is often used to access remote Linux systems.  As the name suggests this is secure (that is the communications are encrypted) and it's used for very many things in the Linux world.  

Today we'll just be talking about using SSH to open an interactive terminal on a remote machine called jumpbox.tpac.org.au.

### A note on terminal emulators

This lesson assumes you understand about [chosing a terminal emulator][chosing-a-terminal-emulator] and that yours supports native UNIX commands.  Otherwise a brief recap:

*If you're on OSX or Linux* you can use the terminal emulator already installed on your computer, no need to do anything else.

If you're on Windows and you chose an emulator with a local terminal (such as [MobaXterm][mobaxterm]) keep reading, these instructions will work for you too.

But if you're on Windows and chose to install [putty][putty] then these instructions won't work.  Consider doing the tutorial on choosing a terminal emulator.

## SSH authentication; passwords vs keys

When we connect to a remote computer, we need to tell it who we wish to connect as; our username.  If you specify no username then the connection attempt will use the username on your current computer.  In this example we're going to connect as user1234 but you should use your own username instead.

```bash
ssh user1234@jumpbox.tpac.org.au
```

(if you don't have a username then consider [requesting a TPAC HPC account][hpc-access-and-login] or perhaps provisioning a Nectar instance and connecting to that using SSH instead)

We now need to prove to jumpbox.tpac.org.au that we are indeed user1234.  This is called authenticating and there are two ways to authenticate; via password or via ssh key.

### Connect with password

This will be the most familiar mechanism, but is less secure than key based authentication.  Connecting with a password is pretty straight forward, we simply start our Terminal and use the ssh command:

```bash
$ ssh user1234@jumpbox.tpac.org.au
user1234@jumpbox.tpac.org.au password:
```

We can see here the server jumpbox.tpac.org.au is asking us for our password which we can go ahead and enter.  If you get the password wrong, you'll usually be given two more tries.  On some systems you may be locked out temporarily or permanently if you make too many mistakes.

## Connect with key

SSH keys are a preferred method of authenticating over SSH and if one is available it will be used before prompting you for a password.

SSH keys are generated as a pair where a *private local key* is paired with a *public remote key*, is used to secure all kinds of online services, from [GitHub][github] and [Launchpad][launchpad] to Linux running on [Microsoft's Azure][azure] cloud.

Before you can connect to a remote computer using your ssh key, you must first generate it, and then install the public key on the remote computer.

## Generating Keys

### Passphrase considerations
Duration: 1:00

When creating the SSH key pair, as shown in the following steps, you can choose to either lock your private key with a passphrase or use no passphrase at all.

Adding a passphrase requires the same passphrase to be entered whenever the key pair is used. Not adding a passphrase removes this requirement. For this reason, creating a key pair without a passphrase is more convenient and potentially essential for certain scripts and automation tasks. But it's also less secure.

If a third party gains access to a private key without a passphrase they will be able to access all connections and services using the public key.

A good compromise between convenience and security is to generate a separate key pair for each service or connection you want to use, adding a passphrase only for critical services. If you suspect a key has been compromised, simply generate a new pair for that service and remove the less secure key.

![screenshot](https://assets.ubuntu.com/v1/53c41ab4-windows_ubuntu_keygen.png)

## Key generation with Ubuntu/OSX/MobaXterm
Duration: 2:00

Starting the a terminal on each of these is subtly different:

- on OSX, just start the "Terminal" application.
- same on Ubuntu 18.04 Desktop
- in MobaXterm you want to start it up and click "start local terminal"

### Generate Keys

Because all these sofwares share a similar heritage, the key generation process the same. Run the SSH key generator by typing the following:

```bash
ssh-keygen -t rsa
```

You will be asked two questions. The first asks where to save the key, and you can press return to accept the default value. The second question asks for the passphrase. As discussed, entering a passphrase will require you to use the same passphrase whenever the key is accessed.

However, the passphrase isn't a requirement, and pressing return (twice) will generate a key pair without one. Consequently, you won't be asked for a passphrase when using your key.

When the process has finished, the private key and the public key can be found in the `~/.ssh` directory.  Public keys typically use the `.pub` suffix. By convention, the private key is usually called `id_rsa` and the public key `id_rsa.pub`.  You can change these if you like, but make sure always know which is which!

### Sharing and/or publishing ssh keys
**It's very important; never share your private key `id_rsa`**  When someone has that file they can authenticate as you.  If someone has your private key your only protection is if you added a passphrase when creating the key.  In that case even if an attacker has your private key they won't be able to use it.

Only ever share your public key `id_rsa.pub`.  If a site asks for your public key, you can either upload it directly, or paste it in.  If you need to do that, just cat it out and paste in the result:
```bash
$ cat ~/.ssh/id_rsa.pub
```

## Key generation with PuTTY
Duration: 3:00

To generate a key pair with the PuTTY key generator, simply run `puttygen.exe` and click the **Generate** button in the window that appears.

You will be asked to move the mouse and press keys to improve the random number generation at the heart of SSH security. After this, the raw contents of the public key will be displayed alongside its fingerprint and a timestamp comment.

Two important fields, *Key passphrase* and *Confirm passphrase*, allow you to enter a passphrase to protect the private key.

Finally, you will need to export both the private and public keys separately:

- to export the *private key*, select **Export OpenSSH key** from the **Conversions** menu
- to export the *public key*, click **Save public key** from the main window

Public keys typically use the `.pub` suffix. By convention, the private key is usually called `id_rsa` and the public key `id_rsa.pub`, but this isn't a requirement. It's common to have many keys with more descriptive filenames, for instance.

![screenshot](https://assets.ubuntu.com/v1/399589eb-windows_keygen_putty_export.png)


## Getting help
Duration: 1:00

Congratulations! You have just generated a SSH key pair! You can now add the *public* key to those services you wish to authenticate, such as [GitHub][github] and [Launchpad][launchpad] to Linux running on [Microsoft's Azure][azure] cloud.

If you need some guidance on using SSH keys, take a look at the [Ubuntu community documentation][commdocs], and if you get stuck, help is always at hand:

* [Ask Ubuntu][askubuntu]
* [Ubuntu Forums][forums]
* [IRC-based support][ubuntuirc]

<!-- LINKS -->
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
