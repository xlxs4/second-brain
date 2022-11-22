ESA Design Booster
#### Introduction

Greetings! I'm Orestis, I come from Greece and I'm the co-science lead in the AcubeSAT project.
AcubeSAT is a project of a student team called SpaceDot and is part of the Fly Your Satellite 3! program.
I've been involved in this effort since almost the very beginnings, when everything was still at a nascent stage.
I'm currently getting to wrap up my studies, and I've joined the team not long after I enrolled in the university, I've worked in different aspects of the project, technical and not, and now I'm responsible for the Science-y stuff.

The AcubeSAT nanosatellite undertaking began late 2018 - 2019.
We've designed and are developing a 3U CubeSat which holds a 2U biology payload.
Our mission is two-fold: we want to establish our idea for a modular platform to perform space biology experiments in CubeSats/small satellites as a working prototype.
Also, we aim to probe the way conditions in LEO (mainly microgravity and cosmic radiation) affect yeast cells at the gene expression level.
To achieve that, the 2U payload is a pressurized vessel which hosts a container with the various compartments to run our experiments.
We'll culture cells in-orbit and then see how their gene expression is altered through acquiring images via our DIY microscope-like imaging system.
We aim to run the same experiment in three distinct timepoints across the duration of our mission, and to do this we've been using a small platform called a LoC to hold the cells and interface them with the various fluidics in a miniaturized version of a biology lab; but more on that at the end.

In brief, we've submitted our proposal in October 2019, took part in the selection workshop hosted here in December 2019, got accepted in February 2020, submitted the TS-VCD (requirements) in April, submitted the first version of CDR in October and had it approved in September 2021, marking the end of the design phase and the beginning of the construction/testing phase.
Right now we are getting ready to run a series of testing campaigns at the ESA facilities, then pass the MRR and be in-orbit by late 2023/early 2024.

#### Context

Before getting on with the actual presentation, I feel the need to underline the overall surrounding context regarding the team I've been and am a part of and the general environment in which we've been undertaking the FYS! journey.
Maybe some of these will align with the environment and the challenges you are to face, maybe not.
1) There's no significant activity in the Aerospace sector in Greece, with the exception of some little companies and organizations that are trying to kickstart things, but we're still at a very early stage
2) On a similar manner, there's not much related expertise or a degree (e.g. in Aerospace engineering) to be offered in Greek universities. These mean it's difficult to get financial or technical support for the project
3) Student's don't gain ECTS credits etc. for being involved in the project to count towards completing a degree. People usually don't get to work at something space-related afterwards, at least in Greece, most enter the team stay for 1 - 1.5 year and then leave

#### Presentation scope

The presentation is focused on discussing some of the programmatic aspects of the challenges you might come to face as FYS! progresses, instead of getting into the nitty gritty things on the technical side. Because I wanted to cover a lot of different topics in a short amount of time, it will be a little free flowing.

#### Presentation Structure

The presentation is split into topics that fall mainly into two distinct categories, the first being project management, while the second follows a more people-centric narrative. There will be advice with an emphasis on the earlier stages of the project, and some good and... not that good decisions to make or avoid, respectively. I'll try cast a more personal light and share some hurdles we've faced and had to overcome, or that we are still facing to this day. Following that tangent, I'll briefly go over some particular examples that greatly affected our team. Then, I'll mention some additional tips, and will close the presentation with an addendum on trying to realize a mission carrying a biological payload, since I've been informed there are some teams interested in working towards that. Because this is somewhat of a niche, please feel free to come have a chat with me after the Q&A session is over, so that we can talk in more detail. I'll share some handles and ways you can reach out to me, I and the whole team are very open and eager to discuss and chime in in whichever way possible.

#### Project management

-   there's always exceptions to rules. Understand the rules, then break them - don't take what I say as a hard absolute to be followed. It's empirical data gathered through observation. Think about what I say and try to understand *why* I say it, throughout the talk

---
**Things are tough**

-   you have to develop skillset from zero - not just technical, but mostly the organizational
-   almost everything is behind closed doors, you don't even know what's out there, you have to learn but how?
-   you have to find support (e.g. from university)
-   you have to ensure infrastructure (e.g. machines) - might be something very generic to get prototypes, might be something very specific related to your payload. Getting access to required infrastructure might be almost trivial in some cases, near impossible in others. You'll face this sooner or later, start thinking about it as early as possible
-   invest in open-source and the community. There's people you can learn from, if not teach - talk a little bit about open-source and how it has helped us and others. In any case, do some research for what's out there. FYS! is about CubeSats. CubeSats are very affordable and easy to build and verify, which means in turn that they are very approachable and that a lot of people who are somehow involved with a similar mission do not belong in the space industry, meaning there's a wealth of information that isn't as strictly regulated
-   you got help from ESA, experts (esp. the experts), reach out - a lot of experience that you can't find elsewhere. Don't be afraid to ask because it might seem like you haven't done your research; it's an educational program and they want you to succeed. Remember that they've went through the whole journey multiple times. This is very crucial to take advantage of as early as possible. They won't just help you solve problems, they might give you fundamentally new ideas and paths to explore
-   other teams participate in FYS!; be in touch - in other FYS! versions and other related projects, we've helped and received helped

bridge: you can get help, and you will need help, because:

---
**Scale up**

-   there's no leadership voice outside of the team, the organization has to be DIY - biggest factor towards your success, no one will help you, and you won't have expertise. It's one thing to learn how to blink LEDs, and another to learn how to run a team of 40 people to meet strict deadlines in a very demanding project
-   COVID hit, and it hit hard. Why? - a good segue, we had to rethink our organizational structure due to limited physical access. A hybrid scheme works best
-   you'll eventually have to scale up, time and time again. How? - your organization must not only stand the test of "now", but also be future proof
-   find good infrastructure, platforms, esp. for organization - can't stress this enough. Communication, tracking and finding information, project planning and management. Don't be pushing things back because you have a deadline to meet. Don't be afraid to invest early, plant the seeds; they will bloom later.

**Information transfer**

-   try maintain information transfer at all costs - our biggest problem
    -   documentation is always needed after completion (Akin's law), it almost never gets written post. If you come to me after I announce that I'll leave and say hey, can you write documentation and/or train new members? It will never happen. It will be sub-optimal at best

bridge: TODO: organization

---
**Organization: the small**

-   keep minutes, have agendas, don't recycle topics, end each topic with an action, make the most out of a meeting
-   cross-team meetings are very important
-   hold concurrent sessions, frequent meetings, be transparent always

bridge: on a more general note, ...

---
**... and the big**

-  you need SYE, aka systems overview: for management, always see the forest, not the tree - how do all the pieces interact with all the other pieces?
-   always be wary of cross-dependencies - some work that needs to be done needs other work to be done first; or I'm needed at A but I'm also needed at B
-   constantly track things, move deadlines appropriately, be on top of things - you'll come to find out that you'll be setting a deadline and it will be way overdue and then you'll have to set a deadline anew and do that because it helps you know where you are and where you need to at all times
-   be agile, especially in the beginning. Find what's good for you. Understand _why_ it's good for you - purposely talking in a loose frame and giving general comments, self-reflection is the most important thing

bridge: exploring a path that you might later on decide that you won't follow, playing with the design, the structure, being bold. You have time, you can afford to make mistakes

---
**Calm down**

- you'll screw up, constantly. Relax and learn from it - it sounds very cliche, but it holds so so true. We've had so many situations where things almost derailed and came close to crumbling down because people were losing their minds. Relax, be calm, assess the situation, do your best, learn from any mistakes and move on. In the grand scheme of things, it probably doesn't matter that much
- diffuse situations, avoid crowd mentality - we've had "critical" situations dozens of times, we're still here
- remember, everything's gonna be alright
- if it isn't, not to worry. It's an educational program - I'm not trying to set the bar low here, things are very challenging and you should strive for excellence, but you have to understand the nature of the program and that the ESA people are here to help and that they know you will commit a lot of mistakes. The thought that they expect you to make mistakes is very liberating, because you will make mistakes and you might think that the consequences will be way bigger than they actually will be. I've noticed that they even get anxious if time passes and you don't seem to be having any problems. Plus, having a problem is great because you know that something is wrong, you probably know what it is, and you will eventually figure out a way to fix things. That's way better than sitting awkwardly wondering whether there's a problem looming around the corner waiting to bite you when you're not looking 
- try to build a momentum, expect a momentum to be built, then ride it, but guide it too; don't let it carry you - I keep saying that things are difficult; you'll find it difficult at first with a lot of things, for example with the organizational structure. It will require a lot of effort in the beginning, it's like a slope where, if you're doing it right, little by little it will get easier with time. Our case happened after we delivered the first CDR version successfully, things somewhat got automated, everyone knew what to work on, communication was frictionless, new members were seamlessly integrated, but you have to always keep things in check and revisit things. We did this mistake and cracks started to appear; it costs us a lot in the end.

---
**The bus factor**

-   be afraid of the [bus factor](https://www.wikiwand.com/en/Bus_factor). The bus factor is when ... and you will come across it and some times there won't be a lot of things you'll be able to do to mitigate it. But also always remember: NO ONE is irreplaceable - (όσες φορές είπαμε να πάμε με τα νερά κάποιου δεν δούλεψε, you're capable). Also trust your gut, same thing as in interviews.
-   this is a very long-term project, it therefore transcends individuals - as we've already stressed, always always always think about the long-term
-   have a plan B, C, D, ... (even about design, _even_ about people (just need it to work - Akin's Law))
- it's a marathon, not a sprint - a phrase of a friend that I feel encapsulates all of this well
    - (... but there will be sprints)

bridge: TODO: long term and patterns and things you must keep in mind

---
**People and problems :(**

-   always find the next gen, preemptively. Otherwise it will be too late and you'll be patching holes. We've had that problem multiple times
-   more often than not, there's a bigger underlying problem, and it has to do with structure. People are usually not the source of the problem - don't be too eager to blame something on an individual, dig deeper
    -   but people CAN be the source of the problem. Never underestimate that. Especially if they are in a position of power, either organizationally or due to technical expertise
    -   don't make someone coo lightly (i.e. don't endow with power lightly). We've had that problem happen way too many times. It's better to leave a gap than to shoot yourself in the foot this way 


#### People management

**People can also be tough**

-   Again, there are a lot of difficulties you'll face when you're trying to get people to collaborate to see this through. There's some similar questions to ask yourselves. The first is how do you find someone to do the boring work? There will be a lot of it, filling spreadsheets, searching for manuals... Especially if you have to hold events and have a social presence too 
-   it's a demanding project without rewards (monetary, ECTS...) - how do you get people to do volunteering work? Because they want to do it. Therefore, you have to make sure they want to do it *a lot*
- How do you get ordinary people to do the extraordinary? You'll have to face great technical challenges while at the same time, constantly support and get the others pumped, be there to mediate in case any conflicts occur, etc.
- taking initiatives is vital - that has been one of our biggest complaints about members. There's new ideas someone has to think, and there's work that no one will do unless someone decides to take it up by themselves. It also helps tremendously in fostering an environment where people feel their peers are motivated
- how do you ensure meeting participation?

-   HR - remember that you should think about how you approach these things too. A good example and place to start might be "Leadership That Gets Results" by Daniel Goleman in HBR. This is recommended for you to see that there's a lot of thought that can go behind things (TODO the report about collective meetings) and a lot of different ways you can approach someone
-   physical presence is vital
-   expand beyond the scope of the project, hang out, do cool things on the side - This team was to me something way way more than just the project. I've learned a ton, met cool people, made friends, found out what I want to do academically, etc. And this is what's kept me working in the project for so long ;)
-   the project requires heavy investment. This means it will overlap with other areas of the member's lives. You have to take that into account and learn about other areas of their life in order to effectively support them. This goes hand in hand with forming groups and being part of a gang

---
**Talk!**

-   ALWAYS face your problems, always speak, always communicate - hoarding problems under the rag instead of facing them is a very well known human tendency. I find that the more long term the thing you're not doing is, the more catastrophic the consequences will be when the time comes to face them. Again, this sounds like a cliche, "just do everything in time" so I will give you an example (TODO: mention EPS)
-   communicate problems to ESA - again, they're hear to help. The sooner the learn about something the better. They'll always appreciate you being upfront, trust me. Don't put yourselves into rabbit holes you'll then have to dig out of
-  feedback is crucial, it's all about feedback cycles - This is by far the most important think to take out of this talk. Feedback requires good communication channels, so first build these. Then learn to give feedback. Learn to receive feedback. Provide people with a lot of different ways they can give feedback. Make sure that there's always more than one person (that hopefully occupies a different position in the team) for someone to speak to. Feedback cycles is the way we get better. Again, make sure to do everything you can to have people a) giving feedback and b) receiving feedback and acting on it
-  praise in public blame in private (not always) - a good reminder to keep in mind mostly the praising 

---
**The leadership behind the leadership**

-   set up a "core" team of people to serve as the backbone of the team at all times - This is, organizationally, what helped us make it. It also affected our progress severely when we lacked it
-   who thinks about the team and not just technical work or events? - That's how you can find the people you'll rely upon
-   decisions will always upset some people. The question is which - If all goes south, side with the ones that will carry the team on their shoulders. They're your most important asset. Always consider how a decision might affect them and their motivation
-   invest in those you believe will carry the team forward, not from a technical viewpoint
    -   this might mean not going with the majority. The majority will also blindly follow whatever, it's a formless mass to give shape to (oops)
-   don't shadow-government much - this all might go against transparency and people will eventually catch up to that. Be transparent almost always

---
**Help them help you**

-   people won't do things they don't want to do forever - never forget that, try to find an alternative
-   there's always someone out there that wants to work on what you don't. Find them
    -   newer members can find something more exciting, _resource allocation_
    -   also talk about the chef tasks book ("Work Clean"), you should also include things in feedback on how to work more efficiently, etc.

**Help them help you: Vol 2**

-   don't leave anyone on their own
-   set group tasks
-   set small, well-defined tasks. Make the members feel and visualize the progress
-   make sure everyone is on the same page regarding the high-level roadmap
-   give people things they might not love but that are important, and things that aren't important but they love doing - try to find asteris top model
-   progress is seldom linear, or apparent. Try to make it apparent, but have that in mind
-   involve people and throw problems at them (but always be there when needed) - don't be afraid to throw problems at them, that's how they grow

---
**Fluff**

Some other things I wanted to make time to mention but couldn't group with the rest of the topics

-   sometimes you have to be quick to arrive at a decision. That might mean you won't have time to get everyone to agree with said decision
-   recruitment is key. You'll also need to establish presence in the uni(s) to get people in REC
-   [Akin's Laws](https://spacecraft.ssl.umd.edu/akins_laws.html) - HEH

TODO: talk about the importance of having a vision, of having some pillars, of your work being multifaceted and extending past just some research topic, etc. Mention our mission as an example and explain why that's so so so important (e.g. to screenshot apo random)

###### Miniaturization of cell culturing instrumentation
###### Ensuring biocompatibility of payload materials
###### Regulating temperature and pressure to decouple cell survival-behavior from other space stressors (e.g. radiation)
###### Using methods for autonomous measurements (e.g. spectroscopy, microscopy)
###### Preparing predictable long-term biological sample storage methods before launch
###### Engineering reliable readouts for cell viability/metabolism
###### Standardization of common wet lab methods to meet space engineering requirements/procedures
