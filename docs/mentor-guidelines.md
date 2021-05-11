# Summary
This guide outlines strongly recommended practices when serving as a mentor hosted by OS hackathon. These practices have been suggested by previous mentors and organizers since 2018. 

Before reading through this guide, you are encouraged to [read about hackathon taxonomy](https://www.oshackathon.org/resources/what-is-a-hackathon) so that you are familiar with the different types of hackathons. Knowing the types of hackathons will help you best position yourself as a mentor and subject-matter-expert for hackathon attendees.

If, at any time, you feel something is missing or needs to be adjusted in this document, to open an issue or submit a pull request at https://github.com/os-hackathon/hackathon-docs

# Behavioral Guidelines
In an effort to mitigate misappropriations at our hackathon events, we provide clear behavioral guidelines:
* A hackathon is not a commercial space.
* A hackathon is not a career fair.
* A hackathon is not exclusive and/or prohibitive.

In an effort to stimulate appropriate behavior at our hackathon events, we provide clear guidelines:
* A hackathon is an educational space.
* A hackathon is a networking event.
* A hackathon is inclusive and supportive.

Any violations in these guidelines will result in dismissal from events as well as consideration for removal from event partnership opportunities in the future.

# Guidance for all hackathons

## Identify the compute platform you will use at the hackathon
At a hackathon, it is likely that mentors and attendees will have access to a variety of compute resources. This is especially true when porting applications from one platform to another. Make sure that everyone on your developer team, including the mentors, has access to the same compute resources. 

Whenever possible, it is important that you and your team access the compute platform before the hackathon. This gives you and your team the opportunity to understand the environment setup and job scheduler on that system. Learning how to move around on the chosen compute system before the hackathon will help maximize the time your team will spend on coding.

# Porting & Optmization Hackathon

## Pre-hackathon Preparation

### Your team’s application should compile, run, and give correct answers

During the application process, the organizers try to find applications that are ready for a porting and optimization hackathon. Additionally, organizers do their best to make sure a variety of compute resources are available so that teams can build and run their code as is. Make sure that your team has a well documented process to build and test their application before the start of the hackathon. This often includes having pre-configured simulations or demonstration examples that can be used to verify proper execution.

### Your team’s application should be self contained
Ideally, the focus of the 5 day hackathon should be limited to a few thousand lines of code. System dependencies (e.g. Cray computing environment, hard-coded paths in build system, etc) should be removed. If there are external dependencies (e.g. NetCDF, HDF5, BLAS/LAPACK) that are required, it is imperative that these dependencies, along with the required compilers, are communicated to the organizers and system administrator well before the event. At some events, this communication happens during the registration process.

Work with your team to identify external dependencies and communicate these requirements to the organizers and system administrator.

### Your team’s code should be configured to run in a short amount of time
During the 5 day coding sprint, you and your team will be making modifications to the code base and running the code to ensure correctness. Successful teams have found that many small changes, accompanied with frequent code execution and output verification, is a desirable workflow. This means that you will be running the application a lot. 

To fit this workflow and be productive at the hackathon, it is necessary that the test case used to verify/validate the code runs in a short amount of time; this permits rapid feedback that guides changes you will be making in the code. 

### Your team’s code should run on one process 
If your team’s application is being ported to the GPU for the first time or if you are working on kernel optimization (and the problem size is small enough to fit on the target GPU) it’s recommended that your team’s code and example test case run in serial or only on a single GPU. Working with MPI in addition to a GPU programming API can result in more hurdles to overcome that just a single GPU application. 

Even if the end goal is to run on multiple GPUs, if there is no GPU offloading in the code yet, it is highly recommended that the initial focus be on a single GPU application. This is more than enough work for a single hackathon. Optimization, such as setting up GPU-to-GPU communication and tuning for the target architecture can take up a hackathon itself, so unless this is the focus of your time at the event, it is recommended that you target a single GPU.

### There should be a method for automatically verifying the code’s output
Although the primary goal for many teams is to have their code run faster on GPUs, the ported or tuned application should be producing the correct results. Because of this, your team should have a fairly automatic way of robustly verifying the correctness. Integrated metrics, such as RMS values, can hide changes in the produced results. Ideally, binary files that store the program’s state (e.g. the velocity, temperature, and pressure in a fluids code) should be compared against a reference set using “diff” or some hash function comparison.

When actively developing/debugging, it’s a good idea to generate the reference data and the “modified code” data using floating-point safe compiler flags. Only use less safe optimizations when benchmarking. In the event bit-for-bit reproducibility cannot be achieved relative to reference output, it’s good to have an application (written by your team) to compare two sets of application output.

### Generate a call graph and profile of the code before the hackathon
As someone who did not develop your team’s code, it is useful to have a call graph on hand that highlights hot-spots in the code and depicts the relationship between subroutines/functions. An inexpensive way to do this is using valgrind’s callgrind tool and kcachegrind to visualize the callgraph. 

Below are the steps for doing this on a linux system. Note that valgrind and kcachegrind need to be installed.
* Compile the code, from scratch, with the `-g` compiler flag enabled.
* Run the code with `valgrind --tool=callgrind`. For example
```
valgrind --tool=callgrind ./my_exe
```
Running your application with callgrind generates a file, callgrind.XXXX.out, where the XXXX are replaced with the process id (assigned by the OS) for the application. This file can be visualized calling kcachegrind from the command line.
```
kcachegrind
```
Explore the GUI window and find the tab labeled ‘call graph’. Once you have the call graph in view, you can right click and export the call graph to a png.

Alternatively, you can use the [hpctoolkit](http://hpctoolkit.org/) and [hatchet](https://github.com/hatchet/hatchet) to obtain a profile and callgraph.

## During the Hackathon 
### Initial Presentations
On the first day of the hackathon, in the morning, a member of your team will present an overview of the application and the goals for the week. The presentation should have 3-5 slides and take no more than 5 minutes to present. Your team should communicate 
* Who they are
* What the application does
* The algorithm(s) that occupy most of the runtime currently
* The target for the week

The goal of the initial presentation is to present your plan clearly to other attendees, organizers, and mentors to get feedback on the approach. This helps make sure your team is on the path to success!

The presentation should be designed to communicate to other attendees at the hackathon. Typically, there is a wide variety of scientific domains in addition to computer scientists at the hackathon. Showing equations and explaining the impacts of the science does not usually help achieve the goal of these initial presentations and is therefore not recommended. 

As a mentor, make sure the goals of the initial presentation are communicated to your team. Help them develop a short and succinct presentation to get feedback from other attendees.

### Daily Scrum Sessions (Stand-ups)
Every morning, each team will give a short (2-3 minute) update expressing
* Where they are now
* Where they are going
* Where they are struggling

The goal of the daily scrum sessions is to check in with everyone and obtain additional feedback from other groups. We have found that, despite domain science differences, teams often come across the same hurdles are willing to share their solutions with others. Typically, we have asked mentors to deliver the updates at the first scrum session.

The presentations for the scrum sessions should include profiles and code snippets. Ideally, each team would show routine speedups/slowdowns for the routines they are actively working on. At these presentations, no equations should be shown and there is no need to reiterate the scientific background of the application. The goal is to let everyone know where your team is and to seek input to help get past hurdles.

## After the hackathon
### Publications and Recognition
We recognize that you may be volunteering your time to help out at a hackathon. You are encouraged to push your team towards publishing their work. Becoming a mentor is a good mechanism for making new connections and becoming a contributing author on scientific publications. Additionally, you can ask your teams, at the very least, to recognize your contributions and assistance in the code development in any of their future publications with the code you worked on. Asking them to include an acknowledgement in a publication is usually well received and helps recognize your contributions to the community. As an example : 

*“We’d like to thank < Mentor Name > for their contributions towards porting and accelerating < Software Name > for use on < target compute system >. This work was accomplished thanks their expertise and patience at the < Hackathon name >.”*

