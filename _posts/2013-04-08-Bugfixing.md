---
layout: post
title: Bugfixing
---

A few weeks ago we were in the final stages of preperation to launch our new site at work, one of the largest discussion forums in Australia.

Our user base are largely of an older demographic, who have grown very accustomed to the way that the site worked, and have adapted how they use the internet to fit perfectly with how our old site works. Suffice to say, the old site is filled with a large number of anti-patterns.

When introducing users to the new site over our beta testing periods, we were shocked to find out that many of our users downright hated the new site. The site was influenced by the latest trends in design and development, but they didn’t care, because in their eyes compared to what they were used to in the old site, the best-practise UX and UI was hard to navigate and use, with too much whitespace and a confusing thread -> post hierachy.

- - -

Our forum has a ‘like’ feature, where users can like other users’ posts, but not their own. Our community administrator, who is a prime example of one of our average users and was initially very skeptical of the new site, found that sometimes when liking another users’ post it would display a notification saying “you can’t like your own posts”. Obviously this is a bug, so I went to investigate, but after trying for a good 5 minutes I was unable to replicate the issue so I set it aside for later.

The next day I spoke again to the administrator, and asked her to try to replicate the issue for me. Sure enough, within a few minutes she reproduced the issue consistently and provided screenshots. I tried to also cause the error but it worked perfectly for me still, so I switched into her account. Sure enough, it was broken.

I remembered that I was using a [regular expression](http://en.wikipedia.org/wiki/Regular_expression) to extract the users’ id from their profile url, which I was then comparing to see if the post being liked belong to that user (hacky I know, but it was effective). I tested out the regex and sure enough it was only capturing the last digit of the users’ id. I made a single character tweak to the regex and sure enough it started working as intended.

- - -

Simply by working together on fixing the bug, with both myself and the administrator being essential elements in the solution reinforced that we were on the same team. Even though I’m working to build a site that the users might not like very much, and the users have opinions of disdain to the new site that I can’t relate to, by working together on this issue it exemplified the fact that we both want the same thing - to make the forum as good as it possibly can be.
