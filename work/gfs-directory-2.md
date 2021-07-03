---
layout: page-back
title:  A New Community Directory
description: The <strong>Community Directory</strong> is a tool to help members from the Google for Startups communities finding their people
client: Google for Startups
client-logo: https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Google_for_Startups_logo.svg/1280px-Google_for_Startups_logo.svg.png
tags: [UX research, UI design, Front-end Development]
image:  '/images/work/gfs-directory.png'
---
<!-- > In the future, robots will do all the work, so the only reasonable profession to pursue is to build and repair robots (until they repair themselves!)
–<i>Young Ivo, 1998</i> -->

Your first day at a <strong>co-working space</strong> is pretty much like your first day of school. Usually there's someone that explains to you the schedule, the rules and where you can pee. 

You know that you have to take your own stuff (say books, say laptop) and some money for food, but as soon as you get there you start realising that you don't know anyone and your life as a co-worker is gonna be pretty miserable if you don't fix that <a href="https://www.urbandictionary.com/define.php?term=asap">asap</a>.

If you're lucky enough to get accepted into <a href="https://campus.co/">one of Google for Startups campuses</a>, you'll be surrounded by founders, amazing technical people and so on, so you'll want to meet as many people as possible while your –typycally six months– membership lasts.

#### Digitalizing our informal knowledge

At that time, <a href="https://codingcarlos.com/">Carlos</a> and I had been part of the Madrid community for 5+ years, so <strong>we basically had met everyone</strong>. When the Campus team started exploring how they could help people connect inside the community, they didn't take long to notice that we might have some insights on that. 

<a href="https://www.linkedin.com/in/eduque/">Edu Duque</a> scheduled a meeting with us that kickstarted the coolest project I've ever been part of. We had a lot of informal knowledge, and this was the perfect chance to organise it; we drafted a simple script, a list of topics that we wanted to understand better and started the first round of interviews.

![Carlos and I, gathering insights]({{site.baseurl}}/images/work/gfs-directory/campus-london.jpg)
*Carlos and I, gathering insights*

The questions where divided into 5 categories: 

- <strong>First contact</strong>: how did you find about the campus?
- <strong>The community and you</strong>: what's your position in the ecosystem?
- <strong>Your own ecosystem</strong>: are you part of other communities?
- <strong>Hiring and getting hired</strong>: let's learn about your hiring/job hunting process.
- <strong>Tools and processes</strong>: how do you communicate with your co-workers? And with your colleagues from the knotting meetup? And with your friends?

<!-- Asking that very same questions in the Tel Aviv community lead to very interesting insights, but you'll have to keep reading to find out. -->

#### Unknown unknowns

We soon realised that the main problem when trying to integrate is that <strong>you don't know what you don't know</strong>. If you randomly talked with Carlos, he'll ask you about your background and find good matches for you. If no one tells you to talk to a connector like him, you'll probably be relatively isolated for a while.

We also found out that the main reason to look for new connections was needing help with a certain tool or technology (say Mixpanel or Python), but if you haven't met at least one technical profile... who should you ask for help? 

To have a better understanding of all the parties involved, their needs, our (legal) constraints and so on, we spent a few days mapping it out in a lovely house in <a href="https://goo.gl/maps/NBEJTvcajmJJyHUm8">Torre del Mar</a>. 

![UX Mapping]({{site.baseurl}}/images/work/gfs-directory/canvas.jpg)
*Me, counting the minutes left to beach time*

For the pilot, we finally decided to build <strong>a simple directory</strong> of people with the ability to search by name, company and skill; the back-end would be a simple Google spreadsheet managed by the Campus team.
User-generated content is risky, so the Campus would provide professional headshots by <a href="https://www.instagram.com/p/B_hgK19jhvD/" target="_blank">Mario</a>, their in-house photographer. 

<div class="gallery-box">
  <div class="gallery">
    <img src="https://storage.googleapis.com/gfs-directory/pic/U/z/UzubL6rgA4mUKX_i5n7Xl.png">
    <img src="https://storage.googleapis.com/gfs-directory/pic/7/K/7K2qmGuWr19TxudHgTFA2.png">
    <img src="https://storage.googleapis.com/gfs-directory/pic/7/g/7gB5n2TNG5b5KpWFmphZP.png">
    <!-- <img src="https://storage.googleapis.com/campus-directory.appspot.com/ddbb/images/User_98_resized.jpg">
    <img src="https://storage.googleapis.com/campus-directory.appspot.com/ddbb/images/user_183_resized.jpg">
    <img src="https://storage.googleapis.com/gfs-directory/pic/7/s/7sGIjuFf8pEDRTBslfPHi.png"> -->
  </div>
  <em>Headshots by <a href="https://www.instagram.com/p/B_hgK19jhvD/" target="_blank">Mario</a></em>
</div>

The back-end was a simple spreadsheet and the front-end was built with vue.js + Vuetify, because: 
1. we had <strong>total freedom</strong> to choose the stack, and we wanted to learn vue.js, so this was a great chance.
2. the directory was going to be promoted by Google as an internal pilot, so <strong>it needed to look like their products</strong>; Vuetify is an implementation of the Material Design principles for vue.js

We started styling our components using their brand guidelines as reference and built a simple layout that worked great in mobile as well as in desktop, but we made a great mistake: despite conducting severall interviews to find out more about community members and their habits, when we started desgining, we ignored the context.

#### Ignoring our very own research

The first version of the directory looked really cool on mobile, but for bigger viewports it was fairly ugly and difficult to use. On desktop, the directory showed a grid of (massive) cards, while for mobile we designed a small variant of our card component to show a vertical list.

![First version]({{site.baseurl}}/images/work/gfs-directory/ss-first.png)
*Yes, the MVP was ugly AF*

We assumed that you wander around the space looking for someone on your phone, so we focused on the mobile UI, following the "mobile first" mantra. That was just plain stupid: if you visit the Campus, you'll see almost everyone sitting at their desk, working on their laptops. Kudos to us.

"Mobile first" doesn't (or shouldn't) mean "build your UI for small viewports and then adapt to the bigger ones". It was meant for an era when clients still told you to make everything "responsive". 
After releasing that first version, analytics helped us realise that <strong>+80% of traffic came from desktop</strong>, so scaling our condensed mobile UI didn't look like the best plan anymore.

From that moment on, we started designing "desktop first".

![Search by skill]({{site.baseurl}}/images/work/gfs-directory/ss-no-filters.png)
<!-- *Search by skill* -->

#### The Search Experience

We designed that huge search bar on the top to gather data from search queries. It was amazing. Some people typed names like "Andrea", skills like "UX" and "WordPress", and we found a surprisingly large amounts of queries like "free beer" and "events with beer" (LOL). 

And before you ask: no, we're not building an event related feature (yet). Go find your own free beer.

We used some of this info to craft a new placeholder indicating what kind of things you can search for in one sentence: "Try <strong>RatedPower</strong> (a well known startup inside the community), <strong>Andrea</strong> (a well known person inside the community) or <strong>UX</strong> (one skill that most of people know–more than PHP, probably)"

But we soon realised that this tool is meant to <i>discover</i>, not to <i>find</i>, so there should be a different way of <i>searching</i>. For that, we released this "quick filter" bar:

![Search by skill]({{site.baseurl}}/images/work/gfs-directory/ss-search.png)
<!-- *Search by skill* -->

We remembered this quote from one of our interviews:

> The ability to see who has a similar skillset to your own is a great icebreaker.

This way, a user could select the skills they're interested in and sort the content in different ways: alphabetically, by program and so on. Implementing that quick filter bar greatly increased profile views and search by skill, so it looked like we were headed in the right direction, but then, Tel Aviv came.

#### Going global

That initial pilot in Madrid had great engagement metrics, so the Google for Startups team decided to turn our little pilot into an <strong>offical product</strong>. We'd scale it to other 3 hubs (São Paulo, London and Tel Aviv), and then to all the remaining campuses (Warsaw, Tokyo and Seoul). No pressure.

Always keeping in mind the "unknowns unknowns", we concluded that we'd need to visit all Campuses to do some on-site research before releasing a product within communities that (almost certainly) had different ways of connecting and communicating. 

The team was absolutely on board with that idea, so they allocated some budget for this "second phase" and we packed up and spent some days in London, Tel Aviv and São Paulo.

<div class="gallery-box">
  <div class="gallery">
    <img src="/images/work/gfs-directory/london.jpg">
    <!-- <img src="/images/work/gfs-directory/tlv.jpg"> -->
    <img src="/images/work/gfs-directory/mad.jpg">
  </div>
  <em>Learning about communities around the world</em>
</div>

#### Community Tools for all

During the last bits of the pre-pandemic world we conducted that research and worked in several improvements for the Directory. We started <a href="https://communitytools.co/">Community Tools</a> with the goal to offer this product to more communities outside Google for Startups, and to develop new open source solutions.

2020 was a tough year for all. Our plans for the directory inside and outside Google had to be put on hold, but you'll soon hear about the new stuff we've been building. If you want to know more about our global research and our design process, <a href="https://twitter.com/ivoriginal">follow me on Twitter</a>. I'm already working on those posts and hope to publish them soon!

<!-- <div class="container">
  <div class="row">
    <div class="col-12 back-home">
      <a class="button button--outline">Back to Work</a>
    </div>
  </div>
</div> -->