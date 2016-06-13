===== Development setup =====

TL;DR - Mac/Linux machine with [[git|Git]], [[ansible|Ansible]] and [[vagrant|Vagrant]]

----

==== Tenets ====

  * Environment parity - development/working and live environment should be as similar as possible.
  * All changes should be tracked and attributable
  * All deploys to test/live servers should be easy for any person
  * Automate everything!

=== eh? ===

For most people, this just means your machine requirement is Mac or Linux. The modern internet runs on Unix-like systems. In order to meet the dev/live parity tenet, they should use the same.

The automation tools are mostly developed for *nix, so don’t work on Windows/Amiga/etc. If you really insist on using something like HaikuOS, then you're responsible for rebuilding automation tools.

You've gotta learn [[git]].

----

==== Setup ====

(Mac)
Install Mac command line tools. These are tools provided by Apple that make your Mac more developery
http://osxdaily.com/2014/02/12/install-command-line-tools-mac-os-x/ This should include git for you.

Check you have Git by typing `git` in the command line.

Install Homebrew. This is a package manager for your Mac. You’ll use it to install ansible...
http://brew.sh/

Install Ansible, via the terminal. Used for auto-updating software on your Virtual Machines

`brew install ansible`

Install VirtualBox - used for managing many Virtual Machines... operating systems... on your computer.
Just the Platform Package in the first section
https://www.virtualbox.org/wiki/Downloads

Install Vagrant - used for auto-managing your Virtual Machines.
https://www.vagrantup.com/downloads.html


That should be enough for running most of our projects

----

A note on automation. Most of our projects use Kevin's [[ansible]] automation scripts https://github.com/skinofstars/ansible-provisioner


