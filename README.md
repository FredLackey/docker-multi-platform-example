# docker-multi-platform-example
Example for using Docker &amp; Docker Compose in Multi-Platform Development Environments

## Goal  
The goal of this repository is to craft a defacto standard for using Docker and Docker Compose in a multi-platform environment.  Do we use BASH trickery, PowerShell scripts, Batch files, Makefile, custom `docker-compose.yml` files per environments?  The goal is for any developer, regardless of their platform, to easily open our repo and crank up a mutli-project solution without jumping through hoops.

## Why is this important?  
While Docker **runs** on all three of the major platforms (Windows, Mac, and Linux), it is a nightmare to configure in Windows.  And, sadly, many large dev shops use all three platforms during the development cycle.  Common features, such as **mapping local paths to volumes** is buggy, at best.  While windows *does* have the ability to run the Windows Subsystem for Linux, and a psuedo-distrobution of Ubuntu, Fedora, or openSUSE, none of these solve the challenges.  Instead, once must use PowerShell in Windows... which is horrible.

## Why is Powershell so Bad?  
In short, Powershell is not a great solution because it does not work 100% of the time.  Sure, you are able to set environment variables manually, within Windows, to make force it to translate paths, but that feature randomly breaks in different versions of Docker Compose *and* many people complain it has never worked at al.  This means you must alter your `docker-compose.yml` to hard code Windows paths which either means a second copy of your file *or* simply breaking it for the rest of your team.

## What about project structure?  
Many of the examples online show a simple project with one NodeJS / ExpressJS service.  However, in the real world, an enterprise solution will have multiple individual projects that must be developed together.  The paths of front-end projects will probably be parallel to back-end projects, thereby creating a rather complex structure for the Docker Context.  This equates to lots of relative pathing in your `docker-compose.yml` file.  And, in turn, th is is where you begin seeing challenges with the advertised Docker Compose techniques.

## Is Docker Compose the problem?  
Within the Docker world, Docker Compose is assumed to be the defacto standard for bringing up a multi-project solution.  Is there something better?  Bash?  Do we crank up each project individuallly using some type of nested `make` script?  We don't neccessarily *need* Docker Compose if there is something equally useful that will take into account the nuances of each platform without passing the burden onto the developer.

----

# Living Repo  
This goal of this repo is to create a living area for people to contribute ideas to.  While I may have started it, I invite everyone to join and contribute their ideas and opinions.
