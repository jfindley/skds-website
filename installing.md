---
layout: page
title: Installing
---

Downloading and installing
---

Signed binaries are coming soon.
In the meantime, to build from source make sure you have a working Go installation of at least 1.3, and that your GOPATH environment variable is set.
Please see [golang.org](http://golang.org/doc/install) for details.

To install the software please run: ```go get github.com/jfindley/skds/...```
This will create three executables under $GOPATH/bin - 'admin', 'client', 'server'.

 * The admin binary should be run on your workstation.
 * The client binary should be run on the servers you're distributing keys to.
 * The server binary can run more or less anywhere, but must be accessible from all client and admin systems.

For extra awesomeness use your configuration management system of choice to distribute the clients, set the server address and add a cronjob to run periodically.  No user intervention is needed on the client end other than this.

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

Congratulations - everything's installed!  Please proceed to [quick-start guide](/quickstart).

