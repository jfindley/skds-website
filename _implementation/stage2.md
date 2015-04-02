---
layout: page
title: Secret sharing
---

Secrets can be shared with either an individual admin/client or a group.  The process is the same in either case.

1. The public key for the user or group is downloaded from the server.
2. The encrypted secret key is downloaded from the server.
3. If the admin only has access to the secret via group membership, then the group private key is decrypted with the users private key.
4. The secret key is decrypted, using either the group private key or directly with the users private key.
5. The secret key is encrypted for the target user or group.
6. This encrypted key is then uploaded to the server.