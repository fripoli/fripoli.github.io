---
layout: post
title: Updating ssh host key on Windows
comments: true
---

If, like me, you are unlucky enough to work in a project where you have no choice but use Windows as your OS you might run into this.

When attempting to ssh, or perform a git action also using ssh, and the host you connect to was, for whatever reason, updated and got a new ssh host key you get this error:

{% highlight shell %}
WARNING - POTENTIAL SECURITY BREACH!
The server's host key does not match the one PuTTY has
cached in the registry. This means that either the
server administrator has changed the host key, or you
have actually connected to another computer pretending
to be the server.
The new rsa2 key fingerprint is:
ssh-rsa 1024 xx:xx:xx...:xx
Connection abandoned.
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists. 
{% endhighlight %}


To fix this

Windows run -> regedit

Navigate to

{% highlight %}
HKEY_CURRENT_USER\SoftWare\SimonTatham\PuTTY\SshHostKeys
{% endhighlight %}

Delete the key with the respective host name

Now you might need to add the new host key. In my case I got it working with plink (PuTTY command line tool)

plink -P PORT_NUMBER -v user@host.example.com
