---
layout: post
title:  "Understanding the Pipeline"
date:   2016-10-01 15:30:00 +0100
categories: deployment pipeline
excerpt: A look at the deployment pipeline and the advantages it can bring.
published: true
---

Today we're going to look at the deployment pipeline. We're going to start with how typical production deployments take place and the pain this can cause. We're then going to introduce the pipeline itself, what it is and what benefits it aims to provide. Finally we're going to look at a real world example, a project where the techniques of the pipeline were fully utilised.

## Deployment Day ##

Deployment day tends to be pretty scary. There can be lots of new features, lots of moving parts and lots of stress and anxiety. We're typically reliant on manual testing to confirm the application is running. Usually involved in calls explaining why deployments are going wrong. They can be unpredictable in their outcome and usually take hours with developers sat trying to make it work into the early hours of the morning.

This is how deployment days tend to feel - painful. This is where the start of our journey to the deployment pipeline began; there must be a better way.

After reading [Continuous Delivery](https://www.amazon.co.uk/Continuous-Delivery-Deployment-Automation-Addison-Wesley/dp/0321601912) by Jez Humble and David Farley and immediately saw potential benefits to delivering software in this way. Our overriding feeling reading the three anti-patterns of deployment was "I'm pretty sure we've done each one of those things". As an introduction, or reminder, these are:

* Deploying software manually
* Deploying to a production like environment only after development is completed
* Manual configuration management of production environments

The key word here was manual. Then came the pipeline, an automated manifestation of our process for getting software from version control into the hands of users. Every change that is committed in source control goes through a complex process, from build into multiple stages of testing and release. This relies on collaboration of a lot of individuals. The pipeline models this process and visualises so we can see and control progress of each change. It also allows us to build quality in, shifting left things like security and performance in the development cycles.

The aims of the pipeline are three-fold. This is to reduce cycle time, improve confidence and reduce errors. 

### Reduce cycle time

Cycle time is the time it takes between a developers checking in code to it being deployed into production. The pipeline aims to make this time as small as possible. To do this it helps to reduce batch size of work being completed at any one time. It also helps us to react to changes to help ensure we're building the right thing.

### Improve confidence

We've spent the time to automate our deployments, therefore, they've been practiced potentially thousands of times before going into production. We also run automated tests on every check-in. Deployments also take minutes, rather than hours. Every time we check-in and our pipeline is invoked, our confidence increases.

### Reduce errors

The aim here is to fail as early as possible and catch any issues as early in the pipeline as possible. Increase feedback loops ([See the third way of the three ways](http://itrevolution.com/the-three-ways-principles-underpinning-devops/)) and visualise the path to production.

The ultimate aim is to make our deployments *rapid, repeatable and reliable*. Making our deployments to production a non-event.

## Deployment day today

This journey started over 18 months ago, and we're still learning but we have come a long way. Our first use in anger came with a project that had an unmovable deadline due to market demands. This approach to using the pipeline along with Kanban gave us the following benefits:

* We could go from developer check-in, to production ready in less than an hours
* We could react to changing business requirements and work on the most important features
* We could release new features, into production environments less than a day before going 'live'
* We delivered all of the original requirements and a lot more generated through frequent showcasing with the business stakeholders

## The path forward

We're really pleased with our progress in this area, it has been underpinned with a change in culture around our approach to gathering requirements, development, testing and deployment. I will share some of our cultural changes in further blog posts, with a particular look at the art of Continuous Integration which has been the key enabler for using the deployment pipeline.

This has been a very brief introduction to the pipeline, for more information I highly recommend reading the [Continuous Delivery](https://www.amazon.co.uk/Continuous-Delivery-Deployment-Automation-Addison-Wesley/dp/0321601912) book which this blog post aims to summarise.