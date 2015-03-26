---
layout: page
title: Groups
---

Groups are one of the best features of SKDS, allowing you to assign a secret to a large number of users or clients at once.
There's no limit to the number of groups you can create, but currently a user may only belong to a single group.  Group types are also seperate - an admin cannot join a client group and vice versa.

Using groups is easy.  You can list all groups with ```admin group list```, and create/delete groups with ```admin group {create|delete}```.  In the list output you will see two default groups and a super group.  These are built-in groups, and they may not be deleted.

To assign a user to a group, use ```admin user group```.  You cannot assign admins to the super group this way, use ```admin user super``` instead for that.  The user will now have access to everything the group has access to.

To assign a secret to a group, use ```secret assign group```.  For security reasons, you may not assign a secret to a built-in group.
