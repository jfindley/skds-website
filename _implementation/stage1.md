---
layout: page
title: Secret creation
---

1. The admin client retrieves the supergroup public key from the server.
2. The secret is read from the disk.
3. A unique key for this secret is generated, we call this the secret key.
4. The secret is encrypted with this unique key.
5. This secret key is encrypted for the super group, and also for the admin.
6. The encrypted secret is transmitted to the server, along with both encrypted copies of the secret key.

