---
layout: page
title: About
---

SKDS is written in Go, by James Findley.  Please raise issues in [github](https://github.com/jfindley/skds/issues), or contact the author at <a href='mailt&#111;&#58;s&#107;d%7&#51;%40&#102;&#37;&#54;&#49;%&#55;3&#116;%6D%6&#49;il%2E&#102;m'>skd&#115;&#64;&#102;as&#116;mail&#46;fm</a>.

## What is it for?

TLS/SSL Keys.  Encrypted secrets for config management systems.  SSH keys.  Really, pretty much anything that needs to be distributed securely.

## Why is this better than my current solution?

Many reasons!

 * Easily update keys across your entire infrastructure, without ever having to connect to individual servers
 * Use groups to distribute keys to new servers automatically.  Auto-scale your environment without compromising your key security!
 * All the benefits of centralised management without the risks.
 * Have a large team to manage? Delegate management of some secrets and groups without giving away access to everything.
 * Guarantee that all your servers have an up to date copy of your secrets without having to put secret data into configuration management

... and many more besides these.

## What can it do?

Fully fledged administration system, built to be used by both large and small teams.  Scales easily to large numbers of admins and servers.

Fine-grained control over access - grant access to either individual or groups of admins and clients.

Currently, we support Linux and OSX.  It may well work on Windows, but that's not (yet) tested.

## How do I use it?

SKDS has a three-part architecture.

The server component holds the data in a database (sqlite and MySQL supported, Postgres could be added with little effort).

The client component is installed on the servers you're distributing the keys to.  This is designed to be very easy to mass-deploy, and requires little local configuration.

The admin component should be installed on the administrator(s) workstations.  Currently it has a CLI-only interface, although various GUI options are being considered.

Signed binaries are coming soon.  In the meantime, follow the instructions on the [installing page]({{ site.baseurl }}installing)
