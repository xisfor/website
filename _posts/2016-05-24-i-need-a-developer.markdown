---
layout: post
title: I need a developer - Effective development resourcing
date: 2016-05-24
categories: process
---

"I need a developer" is an oft heard phrase at business startup meetups. It's a perfectly valid thing to want when you're getting into a technology business, but you need to consider: Is this the right time and do I have the processes in place to get the most out of this?


There are several key problems that impact early stage product development.

  - Understanding of roles and expectations.
  - Communication problems.
  - Dark arts of development.



## Finding your partner == Finding your tools.

Choosing the right tools for the job is a combination of; commercial pressures and developer preferences.

Many developers and agencies will offer you a choice of tools depending on what they know and how much you're prepared to spend. You need to be mindful that your discussions are focused on the core problem, and not your budget or deadlines. A mistake here can be very costly.

  Business: “I want it cheap and quickly”
  Dev: “I’ll go for the simplest solution with best margin”

  Business: “I got budget and I want bells on”
  Devs: “I’ll get to play with the latest toys”

Most agencies use Wordpress because it has great margins. They can do most things with plugins and they don't need to hire expensive developers. Be warned, here lurk flexibility dragons! Your product will end up fitting some 3rd party plugin author's ideas, and not your target market's.

Don't listen to one developer/agency. Talk to different ones who have done different kinds of work.



## Product ownership

Have a discussion early on as to who owns what part of the project. Don't be surprised if, for example, a developer isn't a designer, or an SEO expert.

Consider who, in your relationship, is responsible for the following.

  - market gap identification
  - solution ideation
  - product idea validation
    - user research
  - core features for MVP
  - what technology to build a product with
  - where to deploy solution
  - development timelines
  - development task prioritisation
  - the design
  - user metric definitions
  - online marketing campaign
  - content and SEO
  - scaling for millions of users

If you can be clear who does what early on, there should be far fewer surprises.



## "How long is it going to take?"

Hardest question ever. And one we get wrong all the time!

Worse still, individual tasks are ridiculously hard to estimate correctly.

Consider
  "Could you just put the login in a modal?"

  - Modal script needs to be added.
    - Modal look needs to be styled and tested on desktop, mobile, tablet.
      - Login form page needs a version made that doesn't have headers/footers so it can be inserted into modal.
        - Need to check whether page request is from modal in individual (non-JS fallback)
          - Discover that iFrame approach won't actually work with oAuth as provide uses noframe restrictions
            - Move form to a component on every page that's hidden, and only revealed on modal.
              - Discover that as it's the second form on the page, your frameworks generated CSRF helpers create two codes on the page, and the second form is wrong. Resolve conflicts.
                - As you've done an AJAX login, you need to handle the return state in the browser using javascript, whether that's updating with failed logins, or updating the existing page with user logged in details.
                  - Update test suite.

Devs make an estimate based on what they thought would be the solution. They probably forget a couple of the steps. Oftentimes their initial solution will be wrong and they'll have to find another. By then end, they're rushing out halfcocked work because they've already overrun the initial estimate by 3x. Or... they've already got a comparable component pre-built.

We're all fallible. We all make mistakes. Estimates can go both ways. It's why I am loath to give fixed price. Someone is going to feel ripped off.

Agile, for all its fluff, gave us a great way to estimate projects; the points system.

As a team, you give each feature/story a number of points, based on relative difficulty to other features. If say, all your feature/story's points add up to 200 and the first week you get 20 done, then averaged out it'll probably take 10 weeks to finish.

It's worth taking the time at the start to estimate as a team. Open discussion helps clarify ideas, and promotes understanding amongst the team as to why some things take longer than others. You can also more easily prioritise. The easy way is to start big and narrow down, like "Users" -> "Email based login" -> "password recovery".

Following a discussion based planning and points estimation has several benefits. Less task by task estimation pressure on the developer. It makes project length estimations more realistic. If you've only got 5 weeks for the 200 points worth of stories, you can prioritise, rather than forcing someone to try (and fail) to meet unrealistic deadlines.




## "How much will it cost?"

### "Can you do it cheaper"

### "I'm really looking for a technical co-founder/graduate/someone to do it for their portfolio"

Development time is without doubt one of the (if not *the*) most expensive parts of building a tech business. For this reason, there is a tendency to try to drive down the cost here. Your risk here is getting sub-par, which will probably cost in the long run.

Developers cost more because it's skilled work, and the skills take a long,un-fun time to acquire. Plus we only have a small demographic that's encouraged to learn. And even if you do learn it, you'll only do it for a few years until you consider yourself outmoded and move up to management.

If you want it cheaper, then the simple answer is to do it yourself. I'm not saying learn to code. I'm saying, learn how a product is put together. Figure out your target market, work out what metrics you should be measuring. Do user research and testing with paper prototypes. Write your own user stories, and borrow a dev for a day to estimate. Prioritise and cut.

### Prioritise and Cut

Discipline here pays off. You're better off having the core product built well, than all the features badly.



## Communication

A tired trope to keep saying, but communication is super important. So many times do projects hurt because of people haven't talked:

  - Openly about their assumptions, roles and responsibilities.
  - As a group about expectations, estimations and choice motivations.
  - About how they will continue to communicate and remain transparent.

Don't try to wing-it with communication, get a process

  - Group chat - Slack, Hipchat, Skype
  - Feature tracker - Pivotal Tracker, Trello
  - Bug tracker - Github issues, Freshdesk
  - Code review - Git pull requests

Emails are great for ad-hoc, but things get lost. Don't rely on it for your process.

The important thing is to make your process as transparent as possible. If everyone feels comfortable challenging each other, you'll all be more efficient.

Be conscious and deliberate.



## Summary

 - Focus on solutions and outcome, not tools or costs.
 - Discuss expectations early and often.
 - Estimate the project as a team for maximum transparency.
 - Communicate deliberately.



