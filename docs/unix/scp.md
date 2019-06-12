---
layout: default
title: SCP
nav_order: 1
comments: true
parent: Unix
---

# How to SCP file between systems using SSH

## SCP usage

The official usage for SCP is shown as following:

```bash
 scp [-346BCpqrv] [-c cipher] [-F ssh_config] [-i identity_file]
           [-l limit] [-o ssh_option] [-P port] [-S program] source ... target
```

SCP (secure copy) can transfer files between remote systems or local system. 

SSH Access is one way to provide security over network connection.

> Secure Shell (SSH) is a cryptographic network protocol for operating network services securely over an unsecured network.

If you're using SSH to connect local with remote system, to scp the file between them, run the following command line:

```bash
scp -i [private key] user@local_host:/file user@remote_host:/file
```
