---
layout: post
title: Stopping MongoDB from automatically starting up on Ubuntu
comments: true
---

Edit the file /etc/default/mongod - you'll probably have to create it

add the line

ENABLE_MONGOD=no

restart =)
