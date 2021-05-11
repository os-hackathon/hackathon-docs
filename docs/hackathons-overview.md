# Overview of hackathons

A hackathon (portmanteau of *hacking marathon*) is an event that brings like-minded individuals in an organized fashion to sprint towards a common goal. The word hackathon has been used to describe a variety of events, typically around software or product development. In general, hackathons can be distinguished by their **focus/scope**, **duration**, and **scale**.

For example, [GPU Hackathons](https://www.oshackathon.org/events/2021-amd-rocm-hackathons) have the following attributes:
* **focus/scope** : To port and optimize software applications for GPU hardware.
* **duration** : Typically GPU Hackathons are of five day duration.
* **scale** : Usually about 10 teams of develepors attend, with between 2-6 developers per team.

In all cases, hackathons are meant to facilitate the rapid sharing of ideas to help all attendees progress much faster than if they tackled their problems alone.


## Hackathon Foci & Scope
When naming a hackathon, we usually prefix a word that captures the scope of the hackathon. In the above example, a *GPU* Hackathon is a hackathon focused on writing software for GPU hardware. As another example [*CFD*](https://www.oshackathon.org/events/2021-cloud-cfd-hackathon) Hackathon could be an event focused on using Computational Fluid Dynamics tools to solve a real-world problem. 

Since hackathons hold their roots in the software and product development realm, we would like to define a set of prefixes to the word *hackathon* that help people understand what might happen at a particular hackathon. 

### Prototyping Hackathons
Software almost always starts from an idea. Usually someone (or a few someones) has a problem they want to solve and they need to define an **algorithm** that can solve the problem. Typically, this stage involves mathematical modeling, database design, and software specification definition. With the initial ideas worked out "on paper", the individual or team creates prototype software and systems to achieve their goal. 


### Porting & Optimization Hackathons
It's no secret that new compute hardware is always around the corner. With the explosion in hardware diversity, stakeholders and developers are interested in exploring the potential benefits of new hardware, like GPUs, TPUs, and FPGAs for their applications. At a porting and optimization hackathon, teams come with existing and working code with the goal of porting to a new hardware. At some events, minimum acceptance criteria includes
* Your application compiles, runs, and gets correct results
* You can easily test and reproduce correctness on existing hardware
* Your application is under version control (e.g. git, SVN, CVS)

In addition to checking for acceptance criteria, developers are often asked about known hardware and compiler portability capabilities in addition to the target platforms during the application process. This information helps organizers properly pair developer teams with mentors and ensure that the appropriate compute platforms are available during the event.


### Utilization Hackathon
With software developed and supported on target architecture, now its time to teach end-users how to use the software. These types of hackathons are also sometimes thought of as "software bootcamps". However, in typical bootcamps, attendees are provided lectures and a pre-defined set of hands-on exercises to walk through. At a *utilization* hackathon, organizers set the scope based on the software that is being represented/focused on at the event. Software users (attendees) come with their own problems in mind and have some idea of how they may want to leverage the software. The key distinction with software bootcamps here is that attendees define their direction, while mentors/subject-matter-experts share their knowledge to help them achieve their goals.
 

## Hackathon Organization
A hackathon is motivated by a shared hurdle that transcends organization boundaries. For example, the exascale era of computing is bringing more diverse compute hardware to the market and scientific software developers need to update codes to be compatible with this new hardware. Many organizations face this same problem and a hackathon can help bring together individuals addressing the same issue, independent of who they work for or what specific science domain they are involved in.

### Hackathon Organizers
Once a motivation is defined, a team of hackathon organizers form an organizing committee to define the focus(i) and scope(s) of the event. Organizers are often associated with hardware vendors, cloud vendors, open-source software leadership teams, and individuals in leadership roles at educational, governmental, and commercial organizations. 

Organizers are responsible for meeting regularly to ensure a successful event. Tasks often include : 
* Fundraising to cover any compute expenses and time & labor expenses
* Promoting the event to drive applications from attendees
* Reviewing attendee applications to the event
Co-operating with team sponsor organizations  
* Recruiting subject matter experts and mentors to support the attendees at the event
* Identifying compute resources and a compute system provider
* Coordinating communications before, during, and after the event
* Aligning appropriate SMEs with attending teams
Developing hackathon retrospectives for the community

### Mentors & SMEs
Typically, the organizers seek out **subject matter experts (SMEs)** well versed in the science and technology associated with the event scope. SMEs can be paired with individual attendees or teams to serve as dedicated mentors or can be leveraged as a floating resource that answers questions through a live chat service or in-person. 

When serving as a dedicated mentor, the SME should help their team develop a sprint plan prior to the hackathon. Typically, this involves helping the team :
* Create an application profile and call graph
* Identify software testing procedures and code commit & merge procedures
* Develop a well-defined and achievable scope for the hackathon

During the hackathon, paired mentors serve as a dedicated resource for their team. Mentors are encouraged not to write code for their team. Rather, they are encouraged to coach their team through a development process and provide rapid response to questions

### Compute Platform Providers
Ideally, attendees and mentors are all given access to the same compute systems at a hackathon. This promotes tight collaboration across attendees and further aids in knowledge transfer across teams attending the event.

A **compute system provider (CSP)** provides accounts for attendees and mentors and access to a compute platform with tools necessary for attendee success. Typically, this means having a variety of compilers and development packages already available, tested, and ready to use. CSPs must also be available for on-call system administration support before and during the event to make sure that all attendees can access the compute systems and have basic information for getting work done.

## Hackathon Duration
Hackathons are endurance events and are best suited as auxiliary additions to an attendees toolkit instead of a method that integrates wholly into a project development workflow. Diligent planning and preparation is a key factor in the successful outcome of a hackathon. Success is a measure of a teams ability to complete the goals and objectives they have set for them or set for themselves within the time they are given to complete them. A hackathon with a focus and scope that is pre-determined obviously allows for better estimation for time to success. In general, a hackathon ranges from 3 days to 5 days.

Teams are granted access to a system, and a schedule of support hours, but the focus and scope of their hackathon may grant them access to a system 24/7 for the number of days of the event. In that case, we have seen team members extend their working hours beyond support hours in order to complete a goal or objective. We don't encourage this behavior, but we do not restrict attendees from applying themselves within their own healthy boundaries. Make sure to schedule breaks that encourage rest and relaxation alongside coding blocks on a hackathon calendar. Consider that we typically see exhaustion indicators in the sentiment of attendees in the middle of an event's lifecycle so for a four day event, the end of day two into day three and for a five day event, the third day is what is referred to as the ["trough of despair"](https://entrepreneur.nyu.edu/blog/2014/07/07/lessons-learned-the-trough-of-despair/) ([See also](https://www.raiseheck.com/2020/03/the-mid-implementation-trough-of-despair/)).

In order to maintain attentive and healthy attendance we suggest providing teams achievable and realistic sprint milestones during planning. Clearly understanding the timeline that is available to team members and what they will achieve within it commonly results in a positive outcome. Sprint planning and scoping is a common professional development takeaway for attendees. 

## Hackathon Scale
Team sizes for hackathons typically range anywhere from two to six members. In some cases single individuals are capable of accomplishing the goals and objectives of an event. Many hackathon organizers consider running a small scale hackathon before organizing a larger scale event.
If an event has five teams with six members there could be thirty attendees, five team leaders, ten mentors, two event moderators, a hackathon organizer team of at least three and potentially other interested parties so a hackathon event clearly justifies an organized approach as it scales.