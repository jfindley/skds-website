---
layout: page
title: Installing
---

## Downloading

<table border="0"><tr><th>File</th><th>GPG Signature</th><th>SHA-256 sum</th></tr>
<tr>
<td><a href="/downloads/skds-linux64-0.1.0.tgz">64bit linux</a></td>
<td><a href="/downloads/skds-linux64-0.1.0.tgz.asc">signature</a></td>
<td><a href="/downloads/skds-linux64-0.1.0.tgz.sum">checksum</a></td>
</tr>
<tr>
<td><a href="/downloads/skds-linux32-0.1.0.tgz">32bit linux</a></td>
<td><a href="/downloads/skds-linux32-0.1.0.tgz.asc">signature</a></td>
<td><a href="/downloads/skds-linux32-0.1.0.tgz.sum">checksum</a></td>
</tr>
<tr>
<td><a href="/downloads/skds-darwin-0.1.0.tgz">OSX</a></td>
<td><a href="/downloads/skds-darwin-0.1.0.tgz.asc">signature</a></td>
<td><a href="/downloads/skds-darwin-0.1.0.tgz.sum">checksum</a></td>
</tr>
</table>



## Installing from source

To build from source make sure you have a working Go installation of at least 1.3, and that your GOPATH environment variable is set.
Please see [golang.org](http://golang.org/doc/install) for details.

To install the software please run: ```go get github.com/jfindley/skds/...```
This will create three executables under $GOPATH/bin - 'admin', 'client', 'server'.

 * The admin binary should be run on your workstation.
 * The client binary should be run on the systems you're distributing keys to.
 * The server binary can run more or less anywhere, but must be accessible from all client and admin systems.

For extra awesomeness, use your configuration management system of choice to distribute the clients, set the server address and add a cronjob to run it periodically.  No user intervention is needed on the client end other than this.

Congratulations - everything is installed!  Please proceed to [quick-start guide]({{ site.baseurl }}quickstart).