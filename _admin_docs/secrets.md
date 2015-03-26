---
layout: page
title: Secrets
---

The first step is always to add a secret with ```secret create```.  This will upload it to the database.  As secrets are stored as encrypted blobs in the database, there is a limit on the size of the secret depending on the database in use.  sqlite3 by default supports up to a bit under 1GB, MySQL supports a lot more.  Be aware that encryption and base64 encoding will add some overhead too.

Secrets can be viewed in three ways - you may either list all secrets - ```secret list all``` - or you may list the secrets assigned to a user or group with ```secret list {user|group}```.

Once in the database, you may update the data of a secret (e.g. to update an expiring TLS pem file) with ```secret update```, or delete an old secret with ```secret delete```.

To actually distribute a secret it should be assigned to a user or group with ```secret assign {user|group}```.  If you wish to undo this, you can revoke access with ```secret remove {user|group}```.