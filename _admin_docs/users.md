---
layout: page
title: Users
---

SKDS has two distinct types of users.  Admin users manage the system, add new secrets, etc.
Client users are the servers you're distributing keys to.

Clients automatically register themselves to the server, and will appear in ```admin user list``` straight away.
From there you can assign them to a group, or just assign secrets to them directly.  They can be deleted with ```admin user delete```, but none of the other user commands apply to clients.

Admin users have more power, and generally represent a human controlling the system.
They are created with ```admin user create```.  This will generate a random password for the new user, who will have to change it on first login.  They can be deleted later on with ```admin user delete```.

There are two types of admin users - regular admins and super users.  Super users have access to all secrets, clients and groups.  Regular admins are much more limited, and can only operate on secrets, clients and groups that they have been given specific permission to manage.  Many functions are only available to super users, and deleting all super users is not supported.

A regular user can be promoted to super user status with ```admin user super```.