---
layout: post
title: SSH Tunnel
date: '2025-03-09 13:14:11 +0530'
categories:
  - Programming
tags:
  - SSH
  - Linux
comments: []
---

<div style="text-align: center;">
  <img src="/assets/images/2025-03-09-ssh-tunnel.jpg" alt="SSH Tunnel image" style="max-width: 300px; width: 100%; height: auto; display: block; margin: 0 auto;" />
  <div style="font-size: 0.9em; color: #555; margin-top: 8px;">
    <em>Image by <a href="https://pixabay.com/photos/tunnel-light-grim-dark-art-6786462/">Franz26 via pixabay</a></em>
  </div>
</div>

SSH Tunnelling (also known as SSH port forwarding) is an easy way to access remote services' ports locally (or vice versa), provided we have SSH access to the remote machine.

For developers, this is especially useful when:

- Your laptop lacks the resources (CPU/Memory/Disk) to run the service.
- You need to run long-running commands without keeping your laptop active.

This is especially useful when using web applications which have a UI.

## When

Even within the intranet, opening ports may require security team intervention — an unnecessary hassle for a temporary test VM.

## How

SSH Tunnelling simplifies access:

```bash
ssh -L 5005:localhost:8080 my-user@my-remote-machine
```

This command maps the remote machine's port 8080 to your local port 5005 (you can map any port).

## Advanced Usage

- Tunnels can also pass through multiple jump hosts. See [this SO](https://superuser.com/questions/96489/an-ssh-tunnel-via-multiple-hops)

## Interesting Insights

While exploring SSH Tunnelling, I discovered:

- SSH has a company behind it. See [ssh.com](https://www.ssh.com/) (SSH Communications Security)
- SSH remote forwarding can expose a local service via a remote machine, similar to tools like ngrok (useful if you prefer not to rely on third-party services). This is useful for registering webhooks in services like GitHub. See `ssh -R ...` [details at ssh.com](https://www.ssh.com/academy/ssh/tunneling-example#remote-forwarding)
- SSH Tunnelling can pose security risks if misused, making awareness crucial ([see](https://www.ssh.com/academy/ssh/tunneling#ssh-tunneling-in-the-corporate-risk-portfolio)).

SSH Tunnelling offers a simple yet powerful solution for secure remote access — whether for testing, development, or beyond.
...
