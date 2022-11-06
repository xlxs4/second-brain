
### Structure

"Participating in FYS! from the student perspective"

- Introduction (`@xlxs4`, SpaceDot, AcubeSAT) - `TODO` mins
- Context (things that might be different in our team's case from the norm) - `TODO` mins
- Presentation scope - `TODO` mins
- Presentation structure - `TODO` mins
- Project management - `TODO` mins
- People management - `TODO` mins
- Examples - `TODO` mins
	- EPS
	- SU
	- PL
- Tips - `TODO` mins
- Bio slides ("biological payload development challenges")
	- Intro/scope - `TODO` mins
	- Challenges - `TODO` mins
		- Miniaturization
		- Biocompatibility
		- Cell survival
		- Cell storage
		- Autonomous measurements
		- Automation
- Outro - `TODO` mins
- Q&A - `15` mins

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

The presentation is focused on discussing some of the programmatic aspects of the challenges you might come to face as FYS! progresses, instead of getting into the nitty gritty things on the technical side. TODO: more

#### Presentation Structure

The presentation is split into topics that fall mainly into two distinct categories, the first being project management, while the second follows a more people-centric narrative. There will be advice with an emphasis on the earlier stages of the project, and some good and... not that good decisions to make or avoid, respectively. I'll try cast a more personal light and share some hurdles we've faced and had to overcome, or that we are still facing to this day. Following that tangent, I'll briefly go over some particular examples that greatly affected our team. Then, I'll mention some additional tips, and will close the presentation with an addendum on trying to realize a mission carrying a biological payload, since I've been informed there are some teams interested in working towards that. Because this is somewhat of a niche, please feel free to come have a chat with me after the Q&A session is over, so that we can talk in more detail. I'll share some handles and ways you can reach out to me, I and the whole team are very open and eager to discuss and chime in in whichever way possible.

#### Project management

-   there's always exceptions to rules. Understand the rules, then break them - don't take what I say as a hard absolute to be followed. It's empirical data gathered through observation. Think about what I say and try to understand *why* I say it, throughout the talk

---

-   you have to develop skillset from zero - not just technical, but mostly the organizational
-   almost everything is behind closed doors, you don't even know what's out there, you have to learn but how?
-   you have to find support (e.g. from university)
-   you have to ensure infrastructure (e.g. machines) - might be something very generic to get prototypes, might be something very specific related to your payload. Getting access to required infrastructure might be almost trivial in some cases, near impossible in others. You'll face this sooner or later, start thinking about it as early as possible
-   invest in open-source and the community. There's people you can learn from, if not teach - talk a little bit about open-source and how it has helped us and others
-   you got help from ESA, experts (esp. the experts), reach out - a lot of experience that you can't find elsewhere. Don't be afraid to ask; it's an educational program and they want you to succeed. Remember that they've went through the whole journey multiple times. This is very crucial to take advantage of early
-   other teams participate in FYS!; be in touch - in other FYS! versions and other related projects, we've helped and received helped

bridge: you can get help, and you will need help, because:

---

-   there's no leadership voice outside of the team, the organization has to be DIY - biggest factor towards your success, no one will help you, and you won't have expertise
-   COVID hit, and it hit hard. Why? - a good segue, we had to rethink our organizational structure due to limited physical access. A hybrid scheme works best
-   you'll eventually have to scale up, time and time again. How? - future proof organization
-   find good infrastructure, platforms, esp. for organization - can't stress this enough. Communication, tracking and finding information, project planning and management. Don't be afraid to invest early, plant the seeds; they will bloom later.
-   try maintain information transfer at all costs - our biggest problem
    -   documentation is always needed after completion (Akin's law), it almost never gets written post

bridge: TODO: organization

---

-  you need SYE, aka systems overview: for management, always see the forest, not the tree
-   always be wary of cross-dependencies
-   constantly track things, move deadlines appropriately, be on top of things
-   be agile, especially in the beginning. Find what's good for you. Understand _why_ it's good for you - purposely talking in a loose frame and giving general comments, self-reflection is the most important thing

bridge: exploring a path that you might later on decide that you won't follow, playing with the design, the structure, being bold

---

- you'll fuck up, constantly. Relax and learn from it - it sounds very cliche, but it holds so so true. We've had so many situations where things almost derailed and came close to crumbling down because people were losing their minds. Relax, be calm, assess the situation, do your best, learn from any mistakes and move on. In the grand scheme of things, it probably doesn't matter that much
- be calm, diffuse situations, avoid crowd mentality - we've had "critical" situations dozens of times, we're still here
- remember, everything's gonna be alright
- if it isn't, not to worry. It's an educational program - I'm not trying to set the bar low here, things are very challenging and you should strive for excellence, but you have to understand the nature of the program and that the ESA people are here to help and that they know you will commit a lot of mistakes
- try to build a momentum, then ride it, but guide it too; don't let it carry you - you'll find it difficult at first with a lot of things, for example with the organizational structure. It will require a lot of effort in the beginning, it's like a slope where, if you're doing it right, little by little it will get easier with time. Our case happened after we delivered the first CDR version successfully, things somewhat got automated, everyone knew what to work, communication was frictionless, new members were seamlessly integrated, but you have to always keep things in check and revisit things

---

-   be afraid of the [bus factor](https://www.wikiwand.com/en/Bus_factor). But also always remember: NO ONE is irreplaceable - (όσες φορές είπαμε να πάμε με τα νερά κάποιου δεν δούλεψε, you're capable). Also trust your gut, same thing as in interviews. This is another reason why you want to have a "core" team of people to lead
-   this is a very long-term project, it therefore transcends individuals - as we've already stressed, always always always think about the long-term
-   have a plan B, C, D, ... (even about design, _even_ about people (just need it to work - Akin's Law)
- it's a marathon, not a sprint
    - (... but there will be sprints)

bridge: TODO: long term and patterns and things you must keep in mind

---

-   always find the next gen, preemptively
-   more often than not, there's a bigger underlying problem, and it has to do with structure. People are usually not the source of the problem
    -   but people CAN be the source of the problem. Never underestimate that. Especially if they are in a position of power, either organizationally or due to technical expertise
    -   don't make someone coo lightly (i.e. don't endow with power lightly)

---

-   keep minutes, have agendas, don't recycle topics, end each topic with an action, make the most out of a meeting
-   cross-team meetings are very important
-   hold concurrent sessions, frequent meetings, be transparent always

#### People management

-   taking initiatives is vital, how do you find someone to do the boring work? How do you get ordinary people to do the extraordinary?
-   how do you ensure meeting participation?
-   it's a demanding project without rewards (monetary, ECTS...) - how do you get people to do volunteering work?
-   HR - remember that you should think about how you approach these things too. A good example and place to start might be "Leadership That Gets Results" by Daniel Goleman in HBR
-   physical presence is vital
-   expand beyond the scope of the project, hang out, do cool things on the side
-   the project requires heavy investment. This means it will overlap with other areas of the members' lives. You have to take that into account and learn about other areas of their life in order to effectively support them

---

-   ALWAYS face your problems, always speak, always communicate
-   so much miscommunication and misunderstandings
-   communicate problems to ESA

---

-   set up a "core" team of people to serve as the backbone of the team at all times
-   who thinks about the team and not just technical work or events?
-   decisions will always upset some people. The question is which
-   invest in those you believe will carry the team forward, not from a technical viewpoint
    -   this might mean not going with the majority. The majority will also blindly follow whatever, it's a formless mass to give shape to
-   don't shadow-government much

---

-   people won't do things they don't want to do forever
-   there's always someone out there that wants to work on what you don't. Find them
    -   newer members can find something more exciting, _resource allocation_
    -   also talk about the chef tasks book ("Work Clean"), you should also include things in feedback on how to work more efficiently, etc.

---

-   understand, mitigate but ultimately just be okay with the [Pareto principle](https://www.wikiwand.com/en/Pareto_principle)
-   who gets credits? for what? is their work recognized?

---

-   don't leave anyone on their own
-   set group tasks
-   set small, well-defined tasks. Make the members feel and visualize the progress
-   make sure everyone is on the same page regarding the high-level roadmap
-   give people things they might not love but that are important, and things that aren't important but they love doing
-   feedback is crucial, it's all about feedback cycles
-   praise in public blame in private (not always)
-   progress is seldom linear, or apparent. Try to make it apparent, but have that in mind
-   involve people and throw problems at them (but always be there when needed)

----

-   be calm, diffuse situations, avoid crowd mentality
-   sometimes you have to be quick to arrive at a decision. That might mean you won't have time to get everyone to agree with said decision
-   recruitment is key. You'll also need to establish presence in the uni(s) to get people in REC
-   [Akin's Laws](https://spacecraft.ssl.umd.edu/akins_laws.html) - HEH

TODO: talk about the importance of having a vision, of having some pillars, of your work being multifaceted and extending past just some research topic, etc. Mention our mission as an example and explain why that's so so so important (e.g. to screenshot apo random)

#### Examples

##### ASAT - SpaceDot split

##### EPS

##### SU

##### PL

#### Tips

#### Bio slides

##### Intro/scope

##### Challenges

###### Miniaturization

###### Biocompatibility

###### Cell survival

###### Cell storage

###### Autonomous measurements

###### Automation

#### Outro
