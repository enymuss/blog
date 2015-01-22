---
layout: post
title:  "Google Code-in 2014 - Summary"
date:   2015-01-17 16:00
categories: gci
---

As Google Code-In (GCI) comes to an end, it's a good time to reflect on my experience participating for the first time in the competition and also to see what I've learnt over the past 7 weeks.

Before the competition, when I was looking at the organisation with which I'll work on for the next 7 weeks, I didn't look at what language their code base was. Most used C++, Python, Java and other scripting languages that aren't my strong suit. OpenMRS drew me in because it was putting a huge emphasis on the community. They had a long description about the organisation, a Talk topic asking everybody to introduce themselves and a wiki entry to get us started. The choice was so obvious for me I even thought maybe I should change to somebody else since probably this will be the most popular one. I'm glad I didn't.

Another thing that drew me to OpenMRS was we were both in the same boat. This was their first time participating in GCI and mine as well, so we'll learn together.

As of writing I've completed 6 tasks. This may not sound like a lot but everywhere you go you'll hear "Quality over Quantity.":

###Task #1: Complete OpenMRS developer setup on Windows OS
This was my first task. I started it the first day and it took me over 10 hours to complete it, which is quite a lot. Because a large amount of other students were starting with this task most errors were solved quickly. OpenMRS had a guide on how to install but only then did we discover that there were build errors when using Java 1.8 instead of 1.7 of .6. Next error, when tests would fail during a clean install, was fixed by [@wluyima][wluyima-github] within two days. During the install I was met with a lot of new technologies that I hadn't met with before, e.g. Tomcat, Apache Maven, Jetty, Eclipse IDE for Java EE Developers and MySQL. I had to install and set-up all of them which was time consuming. I tried different approaches to get it up and running. When Maven wasn't running properly from the IDE, I added it to my PATH and tried running it from the command line. Then, I watched most of the videos available to try and diagnose my problem until wluyima patched the error and it compiled correctly.
On the third day I got it running.
<img src="/assets/GCISummary/RichardSzczerba1.png" alt="First image of completion" style="width: 600px;"/>
<img src="/assets/GCISummary/RichardSzczerba2.png" alt="Second image of completion" style="width: 600px;"/>

###Task #2: CREATE A SET OF CODE FORMATTER STYLES FOR OPENMRS JAVASCRIPT FILES
This was a Level 3 task (5 being the hardest). It was very simple to complete as there were already a lot of resources available online. I did it in a much shorter timeframe than the previous task. I settled on styles that Google used.

###Task #3: RESEARCH: IMPROVE THE MODULUS SEARCH ALGORITHM
This was a Level 5 task. Around this time a lot of the tasks were gaining traction (had comments) but this task just stood in the corner and I started with it. There were other tasks in a similar position but Modulus drew me because it was better aligned with my intrest. It was more of a web application then OpenMRS Platform or the Reference Application. I would call this task my first true experience of developing in open-source, a right of passage if you will.
 
[Modulus][Modulus Website] was built by [Elliot Williams][Elliot Williams Github] to make modules for OpenMRS more accessible. It used MySQL, OAuth, OpenMRS ID, Grails, Groovy and Java. But that's only the backend. The frontend is [Modulus-UI][Modulus-UI Github] which used Angular, Node, Grunt and Bootstrap. To make all these technologies work together was very hard, especially for someone who never even made a website. All this was new to me so I had a lot of questions. The set-up documentation was lacking so what ensued was a 28+ mail conversations spanning 24 days and 10 errors. This taught me patience and how much time a good documentation can save.  I had errors concerning OAuth, an improper .config file for Grails and missing important parts of it, lack of git submodules. Then there was an improper clientID between the UI and backend, no MySQL database with information to be displayed and some errors that even though they were displayed worked correctly. Elliot solved all of them, every single time. This led my to create a whole new [wiki entry][Modulus Wiki] on the process which enabled further GCI participates (more on those later) to get Modulus set up and was linked to from the Github Repo's. 

The write-up of all improvements has its own [wiki page][Modulus Algorithm Wiki]. Iw was my first experience with the grails plugin, Searchable, which is built on Lucene. I made a few improvements and submitted a pull request, which might be merged at the end if GCI. It would have been better if we worked on top of others improvements, which would make making the same changes twice impossible and our results would have been more effective.


### Task #4: READ DEPENDENCIES FROM CONFIG.XML
After scrolling through the available GCI-OpenMRS tasks and finding nothing I felt would be worthwhile both for myself and the organisation I started looking into other projects available on JIRA. I was again drawn to Modulus and reached out to Elliot asking him if it was all right for me to do two tasks as part of the competition. He agreed and added MOD-54, MOD-40 and MOD-87. This made me realize how understanding the mentors are and if you suggest an idea they'll probably agree to it.

SO the task was quite simple, just 5 lines of code. But it was useless. It read the dependencies, returned them and that's it. Nothing read it, changed, touched in any shape or form. I wanted to add a finished part not start on it and give it away for somebody else to finish what I started.

After an hour long discussion on IRC (just imagine how long it'd take by email) about how I should go about fully implementing it the the whole Modulus ecosystem and Elliot giving my lines of code that were really useful, I embarked on my ever first backend job.

I had opportunities before on working with a database but I shied away from them, fearing I would break them. Thankfully, git gave me courage to do it (git revert). Now my reading from the config.xml file became useful, by adding a variable and assigning the required modules during a module creation I was able to display it on screen for the user. But after saving, it disappeared and wasn't visible in the JSON file that the server returned. This was due to not adding the variable (with a hasMany status) to the MySQL database.

After it was returning in JSON format properly, I added the UI components for it as well, both in the "Upload new module" section and when displaying a module. Since the dependencies where string I also linked them back to their respected pages to make the download process go as smoothly as possible.

###Task #5: CREATE A VIDEO TUTORIAL SHOWING HOW TO INSTALL & RUN OPENMRS

This task was completed because the last tutorial was from 3 years ago and a lot had changed. A fellow participant already completed a tutorial on how to do it on Windows, but nobody touched the Mac version.

###Task #6: COMPLETE OPENMRS DEVELOPER SETUP ON MAC OS AND REPORT OUTCOME
This task was the same as my first task but it went much more smoothly. I also had some problems so I debugged them and updated the Wiki entry on the subject for future developers.

## Non Tasks
There were a couple items I did that didn't count toward GCI.

### #1: Song:
I created a song to the beat of "Uptown Funk" by Mark Ronson. I didn't get to shot a music video for it but I completed the lyrics and recorded myself singing them.

<audio controls>
  <source src="/assets/GCISummary/OpenMRS_Song.mp3" type="audio/mpeg">
Your browser does not support the audio element.
</audio>

>This click, that upload

>Burke and Paul, that white gold

>This one, for them patients

>each nations

>Straight masterpieces

>Stylin', wilin'

>Livin’ it up in a city

>Got forms on with Hibernate

>Gotta 'like' myself I’m so pretty

>[Pre-Chorus]

>I’m too hot (hot damn)

>Call the doc and the assistant

>I’m too hot (hot damn)

>Make a scribe wanna retire man

>I’m too hot (hot damn)

>Say my name you know who I am

>I’m too hot (hot damn)

>And my repo ain't 'bout that money

>Break it down

>[Chorus]

>Nurses hit your hallelujah (Woo!)

>Users hit your hallelujah (Woo!)

>Devs hit your hallelujah (Woo!)

>Cause OpenMRS gon’ give it to you

>Cause OpenMRS gon’ give it to you

>Cause OpenMRS gon’ give it to you

>Saturday night and we in the ward

>Don’t believe me, just watch (come on)

>Don’t believe me, just watch

>Don’t believe me, just watch

>Don’t believe me, just watch

>Don’t believe me, just watch

>Don’t believe me, just watch

>Hey, hey, hey, oh!


>[Verse 2]

>Stop

>Wait a minute

>Fill his cup put some liquid in it

>Take a sip, sign the note

>Julio! Get the pulse!

>Work in Kandy, Libya, Kenya, Indiana

>If we show up, we gon’ show out

>Smoother than a fresh banana

>[Pre-Chorus 2]

>I’m too hot (hot damn)

>Call the doc and the assistant

>I’m too hot (hot damn)

>Make a scribe wanna retire man

>I’m too hot (hot damn)

>Nurse, say my name you know who I am!

>I’m too hot (hot damn)

>And my repo ain't 'bout that money

>Break it down

>[Chorus]

>[Verse 3]

>Before we leave

>Lemme tell y’all a lil’ something

>OpenMRS, OpenMRS

>OpenMRS, OpenMRS

>I said OpenMRS, OpenMRS

>OpenMRS, OpenMRS

>Come on, code

>branch on it

>If you implement then flaunt it

>If you commit it then own it

>Don’t brag about it, upload it

>Come on, code

>Branch on it

>If you implement then flaunt it

>Well it’s Saturday night and we in the ward

>[Part-Chorus]

>Don’t believe me, just watch (come on)

>Don’t believe me, just watch

>Don’t believe me, just watch

>Don’t believe me, just watch

>Don’t believe me, just watch

>Don’t believe me, just watch

>Hey, hey, hey, oh!

>[Outro]

>OpenMRS, OpenMRS (say whaa?!)

>OpenMRS, OpenMRS

>OpenMRS, OpenMRS (say whaa?!)

>OpenMRS, OpenMRS

>OpenMRS, OpenMRS (say whaa?!)

>OpenMRS, OpenMRS

>OpenMRS, OpenMRS (say whaa?!)

>OpenMRS


### #2: MOD-87 - Fix Scrolling Bug:
While I was working on MOD-54 I completed this task to a working degree but since it wasn't claimed by me on Melange, Parker completed it properly.

### #3: MOD-40 - Add UI Config for Google Analytics:
This was the last task I claimed during the competition. I learnt how to use grunt, the taskrunner, to add a script containing the GA code into every page. Simple and useful. It was a already pull request before the end.

### #4: MOD-66 - "Delete" link is dangerously ambiguous:
I wanted gain a better understanding of the Modulus webpage, so I turned to the UI and completed a fairly simple task of changing the wording and position of the "Delete" button.

I gained a better understanding of Bootstrap's classes, Angular.js templating and DOM. It was accepted and merged into the main repository.

###What comes next...
Thanks to GCI, I had enough strength to tackle my great fears (backend) and learn a lot about production code. Most of my previous projects were my own, so diving in and getting to know an unfamiliar codebase was great! It also opened my eyes to the existence open-source companies (my previous knowledge was only of Linux).

After such an intense 7 weeks, I'll take a step back and focus on my own projects, which were neglected. I'll return to OpenMRS in the near future, to continue helping out in a small but important way, just like I did before.

[wluyima-github]: https://github.com/wluyima
[Modulus Website]: https://modules.openmrs.org
[Elliot Williams Github]: https://github.com/elliottwilliams
[Modulus-UI Github]: https://github.com/openmrs/openmrs-contrib-modulus-ui
[Modulus Wiki]: https://wiki.openmrs.org/display/projects/How+to+install+Modulus+and+Modulus+UI
[Modulus Algorithm Wiki]: https://wiki.openmrs.org/display/projects/Improving+Modulus+Search+Algorithm