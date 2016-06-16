---
layout: post
title: Developer onboarding - or - Not wasting everyone's time
date: 2016-06-16
categories: process
permalink: /blog/:year/:month/:day/:title/
---

Any development team wants a new start to be up and running as soon as possible.

There are a few hard skills and soft skills that will make this happen with the least fuss:

## Clear prerequisites

Have a list of what OSs are supported and what's needed to set a project up to develop.

This is my typical prereque list:

- Linux / Mac with homebrew
- Git
- Ansible
- VirtualBox
- Vagrant


## Repeatability

You could also say "Automate everything!" A new start shouldn't have to spend time figuring out the basics before they even get going.

I tend to use Vagrant, for both environment parity between developers and production (no more "works for me"), and to be able to have single command setups with `vagrant up`.

I also have [my own set of Ansible roles](https://github.com/xisfor/ansible-provisioner) which can help you with common setups.


## Testing your setup process

One shouldn't care for servers, whether that's in production or development. Destroy your environment and rebuild it on a regular basis. Not from a golden image, but from your provisioning scripts. Exercise your setup.

Servers are cattle, not pets. Never be afraid to shoot one.


## Stop trying to be clever

Nothing makes life more difficult than a developer trying to be clever when there was a simpler solution. Sure, sometimes you'll need a truly unique and ingenious solution, but that's gonna be a rare time. Mostly, you should be trying to to make your setup and code as easy for the next person as possible by keeping it simple and obvious.


## If you're non-standard, then document, discuss and document again

If you aren't doing something obvious, then document, discuss, and document again.

Make sure you do pull requests / code review, and be prepared to change your code there and then if someone challenges. If you lead by transparency, others will happily follow.


## Talk about how you communicate

When you onboard, there really is nothing more disconcerting than not knowing how to communicate with your new team. If you have a process in place, like a team Slack, then this really helps others know how to interact with the team.


## Summary

Don't expect people to just turn up and "get it", because that "it" is different everywhere. Guide new starts so they don't have to use up their mental cycles just trying to grok your process.


