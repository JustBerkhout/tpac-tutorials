---
id: hpc-access-and-login
summary: How to request an account on the TPAC High Performance Computing (HPC) clusters.  How to login through jumpbox.tpac.org.au
categories: hpc
tags: tutorial,ssh,hpc,terminal,account
difficulty: 1
status: draft
published: 2019-05-14

---

# Getting an account and logging in

## Getting an account and logging in
Duration: 1:00

### What you'll learn
* How to get a HPC account at TPAC
* How to connect using ssh
* How to authenticate

### What you'll need

You'll need to have completed the easier tutorials in this category.

## Overview of TPAC HPC services
Duration: 3:00

TPAC have a range of high High Performance Computing (HPC) clusters for various uses.  When you request a HPC account the administrators will talk to you about your project and help you select the right cluster for you.

![TPAC HPC Facilities (May 2019)](/images/tpac-hpc-facilities.png)

### Storage and network connectivity:
All systems are provided:
* 100TB of DMF cache
* 70TB of SAS scratch
* 2PB of tape storage
* Infiniband fabric

## Supported usage and modules
Duration: 10 mins

### Supported usage profile

A default user has access to up to 128 cores, and can schedule jobs into a number of queues. For users requiring more compute we recommend the following options:

1. [NCI][nci] (National computational infrastructure).
1. Other [AeRO][aero] (Australian e-Research Organisations).

### Supported Libraries / Modules:

The following is a small sample of some of the modules that are installed.  Use “module avail” to view specific versions provided on the system you are using:
```bash
R
bzip2
curl
gaussian
git
intel
matlab
merlin
mira
modules
ncl
netcdf
null
octave
openmpi
paup
pism
plink
python
rsync
scirun
starccm+
svn
valgrind
zlib
```
## Requesting an account
Duration: 10:00

Accounts can be requested by completing [this form][get-hpc-account] and submitting it.  If you have an existing account, or are not sure, please submit a help request instead by emailing helpdesk@tpac.org.au.

It can take a few days for your account to be created, so please be patient.

Once your account is created you will get an email containing further instructions

## How to connect
Duration: 5:00

Access to Eddy and Kunanyi is uses ssh via jumpbox.tpac.org.au so you should connect to that first:

```bash
ssh YourAccount@jumpbox.tpac.org.au
```

Once connected to jumpbox please read the “Message of the Day” (MOTD) for cluster status and instructions for how to connect to each cluster.

For example, to connect to the kunanyi cluster it might be as simple as:

```bash
ssh kunanyi
```

## Filesystem locations
Duration: 10

### Home directory
Assuming your username is bob:

```bash
Home directory: /u/bob
```

Your home directory /u/bob is shared with all clusters.

Your jumpbox home directory is different to the above and is not shared
with the clusters however you can access your cluster home directory
as /cluster-home/vndr-datawise01

### Scratch
Again, assuming your username is bob:

```bash
Scratch directory: /scratch/bob
```

Scratch is a local filesystem allocated as a temporary working space and
read and writes to this file system will be faster than to your home directory.
You can create data there but you should not leave anything after a job
has completed.

## Applications
Duration: 5

Third-party applications are generally found under /apps.  You will need to
use environment modules to place them into your path.  Currently installed
applications and libraries include:

* the Intel C/C++ and Fortran compilers (various versions)
* CFX
* NetCDF
* FFTW
* editors such as vim, emacs, xemacs and nedit.
* ANSYS
* GAUSSIAN 03
* Octave

On the login node run the command 'module avail' to see the complete list of applications.
```Bash
module avail
```

## Housekeeping and Administration

### Changing Your Password

Password changes are not currently possible due to an interim LDAP configuration.
When this facility becomes available again will be announced in the hpc-users
email list.

### Login shell
The default login shell for new users is 'bash'.  If you wish to change
your login shell you may send a request to helpdesk@tpac.org.au.

### hpc-users email list
When your account is created you'll be added to the hpc-users@list.utas.edu.au [mailing list][hpc-list].  This is an active community of TPAC HPC users, please feel free to reach out and ask questions

## Support and further information
Duration: 10

If you need more assistance and information:
1. Look at our Frequently Asked Questions ([FAQ][hpc-faq]).
1. Create an account to chat with real people at our [eResearchTasmania][eresearch-slack] Slack Workspace
1. Contact our helpdesk via email at helpdesk@tpac.org.au.
1. Refer to our [TPAC facilities][facilities] information.

<!-- LINKS -->
[get-hpc-account]: https://docs.google.com/forms/d/e/1FAIpQLSeiCUaSSvHHUxfPL1L-sFHqgKqLYeyIf4KBsMpd57QCRxzI9w/viewform?usp=sf_link
[hpc-list]: https://lists.utas.edu.au/mailman/listinfo/hpc-users
[nci]: http://nf.nci.org.au/accounts/
[aero]: http://aero.edu.au/
[eresearch-slack]: https://eresearchtasmania.slack.com/signup
[facilities]: http://www.tpac.org.au/index.php/tpac-hpc-facilities-2/
[hpc-faq]: http://www.tpac.org.au/index.php/hpc-faq/
