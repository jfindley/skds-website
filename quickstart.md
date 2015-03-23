---
layout: page
title: Quick-start guide
---

## Setup

Once you've built and distributed the binaries to the correct places, the server must be started.
By default the server expects its configuration to live in /etc/skds/server.conf.  An example configuration file is provided, which uses an sqlite database in the same location, along with some reasonable defaults.
Please make sure that you set the NodeName parameter of the server **before** starting it.  It's important that this is a valid DNS name for the server that is resolvable by all clients and servers, for security reasons.

The server will on first run create the database tables, generate certificates and create an initial user, called admin with password 'password'.
If you want to start again for any reason, simply remove everything from the configuration directory except the config file and restart the server.  Admin and Client systems will need to be reinstalled and their configurations wiped if you do this.

Next get the admin console running.  It needs no manual configuration, you can simply run it on your workstation and it will configure itself, after asking you a few basic questions.  By default it uses ~/.skds for configuration and keys.
The first time you run this, you can use the default account details of:
``` Username: admin Password: password```
You will be required to change these on first run.  As this is the first admin client to connect, you must also run "key private set super" right away.

The client by defualt looks for configuration in /etc/skds/client.conf.  An example config file is provided, most people should only need to change the NodeName to something unique to that client (e.g. hostname) and the Address to point at the server.  You must use the DNS name configured earlier here, not an IP address.

## Basic usage

The admin client has a tree of commands.  help command or command -h will show you usage information for that particular command.

Let's assume you've connected a single client to your server, called client-1.
Check it's registered to the server with: <code>admin user list</code>.  You should see your client listed.

Now let's add a secret to the server.  Let's say your secret is located at /path/foo.pem on the admin system.  We're going to call it foo-2015 and tell the client to install it into /etc/pki/tls/private.

First, add the secret to the server: <code>secret create -n foo-2015 -f /path/foo.pem</code>.  Now we need to assign the secret to the client: <code>secret assign user -n client-1 -s foo-2015 -p /etc/pki/tls/private/foo-2015.pem</code>.  That's it! Done.  Now the next time the client runs, it will download and install foo.pem to /etc/pki/tls/private/foo-2015.pem.
