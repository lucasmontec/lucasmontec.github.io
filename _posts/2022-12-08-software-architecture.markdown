---
layout: post
title:  "On Why Software Architecture Matters"
date:   2022-12-08
categories: General
excerpt_separator: <!--more-->
---

# [Draft]  Why software architecture?

Hey folks! As promised, I’m going to share today a little bit of my vision on why I believe software architecture matters.

For the past few years, I have been working with lots of really talented people on games and real-time multimedia projects. I have had the chance of working on projects that deal with hundreds of thousands to hundreds of millions of users. Projects that ranged from critical business applications with high availability and throughput to tools that were less critical but still fundamental for speeding up the development process, standardizing pipelines, and providing automated workflows. The applications I developed also spread a wide net on the different types of contexts applications can have. I have experienced developing backend monoliths, microservices and on the other side, clients and game clients. And from all of those experiences, there is one thing I believe they all have in common: they are all structures of abstraction.

<!--more-->

## What composes software

What do I mean by “structures of abstraction”? Well, for me, programming is the art of conceptualizing the real world. It is one’s ability to observe something that happens in actual life, understand its mechanics, components, and actors, then translate that into code. That translation part is where the developer starts to create structures of abstraction.

### Abstraction

The abstraction is when the developer understands that a certain thing is an actor, a component or a system on the application, then abstracts most of its properties and capabilities, representing only what matters for the application.

Let's work with a real example, without writing a single line of code. Suppose you have to take out the [trash](https://www.youtube.com/watch?v=i7gIpuIVE3k), the garbage man is coming. When you have such a task, do you consider whether the garbage guy is really coming? Do you think about checking the garbage bags for holes? Do you get gloves? Prepare before hand to tie the bags? Clear a path to where you are going to place the trash?

Those are all things that might happen and that you learn to deal with when they first happen. Those are some of the trash handling mechanics. Things that can occur and that express a relationship between the actors involved: you and the trash bag. You usually don't even think about you as an actor, or the bag. You also are not generally thinking about those conditional responses to natural trash handling events. All of those mechanics are abstracted by you since you probably have handled trash in the past and have dealt with those before.

This is a main part of what a developer does. We look at the world, extract the main things that happen surrounding a certain topic, establish which are the actors and components that exists in that context, and then understand which relationships, events and actions we care about to solve the problem at hand.

### Structure

After we understand which are the pieces of the puzzle and how they might interact, we then start defining our own rules on top of that. We decide how we are going to deal with each interaction, how to represent those using components, tools and code.

Going back to the garbage example, after we define ourselves and the garbage bag as actors, and maybe tying up and moving the bag as actions, we then need to define the structure of these tasks. We can, for example, write a list of actions with some conditions on some of the actions. maybe not tying the bag it it is already tied. Or unlocking the door if it is locked. This is on a lower level of abstraction still. Then we have bigger components, for example the garbage truck. We cannot put out the trash if it is not the garbage collection day. Thus there is a time relationship to be established between the garbage truck actor and you.

The structure starts to emerge organically here. Things that happen define certain layers of responsibilities, contexts where actors and systems live. You become a garbage mover in the garbage access layer. On that layer, actors can access the garbage repositories, on the garbage layer. Garbage movers can move garbage bags between those repositories, thus being able to empty the house trash can and fill the street garbage spot.

![https://lucasmontec.github.io/assets/images/garbagediagram.jpg](diagram showing the relationship between actors. the 'you' actor is tied to the household garbage repository and to the street repository. the garbage man actor is tied to the street repository)

So generally, the structure creates well defined rules and roles between the actors and components. Whereas the abstraction, is the conceptualization or generalization of the actual world. And because of that, I believe software can be seen from a perspective, as structures of abstraction.

## What is software architecture then?

This is a very deep, complex and subjective topic. Software architecture has been defined several times in the past, from several different perspectives and inside different contexts. 

WIP: talk about martin fowler, robert c martin. architecture objectives (reduce human resource cost, adapt the 'soft'ware to its changing requirements). Talk about machines being able to read any code but humans taking a long time to read it. Talk about complexity not being linear sometimes.

