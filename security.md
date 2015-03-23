---
layout: page
title: Security
---

Every effort has been made to make this software as secure as possible.
Security features and limitations are below.

Please note that at no point has this software been audited by a professional cryptographer, so please treat the below with caution.

## Server

The server stores a copy of every secret in the system.  So that a compromise of the server can never divulge secret information, the secrets are encrypted with the excellent [NaCL](http://nacl.cr.yp.to/) library.  The decryption key for the secret is **never** present on the server, even in memory, and is never reused between secrets.

All communication with the server takes place over TLS 1.2.  The certificate and CA for this is generated on the server at first-run, with the CA distributed to all admins/clients automatically for verification and the certificate cached to "pin" the server certificate.

## Client

On first run, a client randomly generates an authentication key, and a separate encryption keypair.  THe former is used to authenticate a client session to the server, and the latter used to decrypt secrets recieved.

Even if both these secrets are stolen, an attacker cannot decrypt any secrets to which the client did not already have access.

## Admin

The admin tool authenticates to the server with a password that is never stored on disk, and is hashed on the server with the [scrypt](https://www.tarsnap.com/scrypt.html) algorithim.  We strongly suggest using a secure password for this.
Similarly to the client, a unique keypair is generated and stored on the admin client.

## HSM support

Every attempt is made to zero secret data in memory as fast as possible, but currently there is no support for HSMs, so secrets must be stored on disk.
If you wish to assist with this, HSM hardware for testing purposes would be greatly appreciated.
