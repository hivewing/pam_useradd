pam module that creates new users on the fly and cleans up
=================================

intro
-----

pam_useradd creates accounts if they do not yet exist on the system.
It only adds a user which can then be logged into with public-key authentication

It also will copy down any credentials from a configured server, to the .authorized_keys file
It will not create a user if the URL returns nothing.


usage
-----

add the following line to e.g. /etc/pam.d/gdm (before other auth
lines):
> auth     optional       pam_useradd.so

... UTSL

security
--------

your default system policies should be set up in a way that new
users don't gain privileges that can be used to damage the system
obviously.

do not use the module with 'su'. It's not safe to be used in setuid
context.
