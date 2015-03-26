---
layout: page
title: Running
---

The client runs once and exits.  We suggest adding a simple cronjob to check periodically for updates from the server.
Assuming you installed the client to /usr/local/skds/client, create a file called skds-client.cron in /etc/cron.d with the following content:

```
*/15 * * * * root /usr/local/skds/client

````