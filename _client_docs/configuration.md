---
layout: page
title: Configuration
---

An example configuration file is provided at [github](https://raw.githubusercontent.com/jfindley/skds/master/_examples/client.conf)

The only things most users should change in here is to set NodeName to a unique name for this client (hostname works well), and to configure the address of the server.

The server address must be the same as the server's NodeName, and must be resolvable by the client.  If this is a problem, consider using an alias in /etc/hosts.