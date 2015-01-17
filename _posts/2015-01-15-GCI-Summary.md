---
layout: post
title:  "Google Code-in 2014 - Summary"
date:   2015-01-17 16:00
categories: gci
---
As Google Code-In comes to an end, it's a good time to reflect on my experience participating for the first time in the competition and also what I've learnt over the past 7 weeks.

As of writing I've completed 6 tasks. This may not sound like a lot but everywhere you go you'll hear "Quality over Quantity." Let's look at those tasks:

###Task #1: Complete OpenMRS developer setup on Windows OS
This was my first task. I started it the first day and it took me over 10 hours to complete it, which is quite a lot. Because a large amount of other students were starting with this task most errors were solved quickly. OpenMRS had a guide on how to install but only then did we discover that there were build errors when using Java 1.8 instead of 1.7 of .6. Next error, when tests would fail during a clean install, was fixed by [@wluyima][wluyima-github] within two days. During the install I was met with a lot of new technologies that I hadn't met with before, e.g. Tomcat, Apache Maven, Jetty, Eclipse IDE for Java EE Developers and MySQL. I had to install and set-up all of them which was time consuming. I tried different approaches to get it up and running. When Maven wasn't running properly from the IDE, I added it to my PATH and tried running it from the command line. Then, I watched most of the videos available to try and diagnose my problem until wluyima patched the error and it compiled correctly.
On the third day I got it running.
<img src="/assets/GCISummary/RichardSzczerba1.png" alt="First image of completion" style="width: 600px;"/>
<img src="/assets/GCISummary/RichardSzczerba2.png" alt="Second image of completion" style="width: 600px;"/>

###Task #2: CREATE A SET OF CODE FORMATTER STYLES FOR OPENMRS JAVASCRIPT FILES
This was a Level 3 task (5 being the hardest). It was very simple to complete as there were already a lot of resources available online. I did it in a much shorter timeframe than the previous task. I settled on styles that Google used.

###Task #3: RESEARCH: IMPROVE THE MODULUS SEARCH ALGORITHM
This was a Level 5 task. Around this time a lot of the tasks were gaining traction (had comments) but this task just stood in the corner and I started with it. There were other tasks in a similar position but Modulus drew me because it was better aligned with my intrest. It was more of a web application then OpenMRS Platform or the Reference Application. I would call this task my first true experience of developing in open-source, a right of passage if you will.
 
[Modulus's][Modulus Website] was built by [Elliot Williams][Elliot Williams Github] to make modules for OpenMRS more accessible. It used MySQL, OAuth, OpenMRS ID, Grails, Groovy and Java. But that's only the backend. The frontend is [Modulus-UI][Modulus-UI Github] which used Angular, Node, Grunt and Bootstrap. To make all these technologies work together was very hard, especially for someone who never even made a website. All this was new to me so I had a lot of questions. The set-up documentation was lacking so what ensued was a 28+ mail conversations spanning 24 days and 10 errors. This taught me patience and how much time a good documentation can save.  I had errors concerning OAuth, an improper .config file for Grails and missing important parts of it, lack of git submodules. Then there was an improper clientID between the UI and backend, no MySQL database with information to be displayed and some errors that even though they were displayed worked correctly. Elliot solved all of them, every single time. This led my to create a whole new [wiki entry][Modulus Wiki] on the process which enabled further GCI participates (more on those later) to get Modulus set up and was linked to from the Github Repo's. 

The write-up of all improvements has its own [wiki page][Modulus Algorithm Wiki]. Iw was my first experience with the grails plugin, Searchable, which is built on Lucene. I made a few improvements and submitted a pull request, which might be merged at the end if GCI. It would have been better if we worked on top of others improvements, which would make making the same changes twice impossible and our results would have been more effective.


[wluyima-github]: https://github.com/wluyima
[Modulus Website]: https://modules.openmrs.org
[Elliot Williams Github]: https://github.com/elliottwilliams
[Modulus-UI Github]: https://github.com/openmrs/openmrs-contrib-modulus-ui
[Modulus Wiki]: https://wiki.openmrs.org/display/projects/How+to+install+Modulus+and+Modulus+UI
[Modulus Algorithm Wiki]: https://wiki.openmrs.org/display/projects/Improving+Modulus+Search+Algorithm