---
layout: page
title: Configuration
---

An example configuration file is provided at [github](https://raw.githubusercontent.com/jfindley/skds/master/_examples/server.conf)

Before the server is run for the first time, you **must** set NodeName to something resolvable by all systems.  Usually this should be the hostname of the server.

For most users, Address can be left as the default - this will listen on all interfaces - but you can configure this if needed.

Under [database], you can configure the type and details of the database.  sqlite3 is chosen by default, as it's simple and requires no additional configuration.  If you want to store secrets larger than a couple hundred MB however, or you're running a very large environment, you're advised to switch to MySQL.  If you want to do this, see an example config at [github](https://raw.githubusercontent.com/jfindley/skds/master/_examples/server_mysql.conf).
Some additional configuration is required for this.  You will need to install MySQL (consult the docs for your OS), create the named database (skds by default) and create a user with full access to the database.  The server will automatically create tables within the database.