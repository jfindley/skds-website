---
layout: page
title: About
---

SKDS is written in Go, by James Findley.  Please raise issues in [github](https://github.com/jfindley/skds/issues), or contact the author at <a href='mailt&#111;&#58;s&#107;d%7&#51;%40&#102;&#37;&#54;&#49;%&#55;3&#116;%6D%6&#49;il%2E&#102;m'>skd&#115;&#64;&#102;as&#116;mail&#46;fm</a>.

## What is it?

SKDS is a highly secure system for managing and distributing files such as TLS/SSL Keys, encryption secrets for config management systems, SSH keys or any other private data.
It is designed to scale to large environments, but be small and simple enough to use almost anywhere.

## Why is this better than my current solution?

 * Easily update keys across your entire infrastructure, without ever having to connect to individual servers
 * Use groups to distribute keys to new servers automatically.  Auto-scale your environment without compromising your key security!
 * All the benefits of centralised management without the risks.
 * Have a large team to manage? Delegate management of some secrets and groups without giving away access to everything.
 * Guarantee that all your servers have an up to date copy of your secrets without having to put secret data into configuration management

... and many more besides these.

## How do I use it?

SKDS has a three-part architecture.

The server component holds the data in a database (sqlite and MySQL supported, Postgres could be added with little effort).

The client component is installed on the servers you're distributing the keys to.  This is designed to be very easy to mass-deploy, and requires little local configuration.

The admin component should be installed on the administrator(s) workstations.  Currently it has a CLI-only interface, although various GUI options are being considered.

Signed binaries are coming soon.  In the meantime, follow the instructions on the [installing page]({{ site.baseurl }}installing)

## What's the risk of losing access to my data?

Aside from the server failing (make sure you back up the server!), secrets can only be lost if you lose the keys of all your super users, and all the keys of admins and clients with access to the secret.