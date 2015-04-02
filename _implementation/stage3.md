---
layout: page
title: Secret updating
---

The first four steps are identical to secret sharing, above.  Once the admin has the decrypted unique key for the secret, then...

1. The new secret is read from the disk.
2. The new secret is encrypted with the original unique key.
3. The encrypted secret is uploaded to the server.

As the unique key has not changed, everyone that originally had access to the secret continues to have access, and all clients will update their secret data on disk.