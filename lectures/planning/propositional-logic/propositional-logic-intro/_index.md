---
title: Propositional Logic Introduction
weight: 91
draft: false
---

# Propositional Logic Introduction

We have seen in the [route planning]({{<ref "../../search">}}) module that for some problems agents do not need to possess significant representational abilities - its enough to represent the environment states as _atomic_.  

We also have seen in an earlier chapter where we introduced a _dynamical system_ governing the state evolution of the environment that a state is composed of variables and such _factored representations_ are key in allowing _reasoning_ at the _belief_ space that are efficiently computed using recursive state estimators. We called this subsystem _probabilistic reasoning_ subsystem and we positioned it immediately after the reflexive perception for a good reason. It is processing a very high 'bandwidth' state information that is noisy and needs to be filtered by - you guessed it - Bayesian filters to make it very useful for the subsequent upstream services of the AI system. 

In this chapter we will see another powerful representation, _internal_ to the agent, that can help agents to _reason_ by expressing assertions about the world. These assertions are called _sentences_ and are expressed in a _knowledge representation language_ that is used to build a  **Knowledge Base (KB)** - a concept central to AI. The KB starts with prior knowledge about the domain and problem at hand and incrementally is updated with the output of the probabilistic reasoning subsystem. 

Lets see a concrete example as described in the figure below,

![abandoned-backpack](images/abandoned-backpack.jpg#center)
*Imagine that the agent is a security robot at an airport and is moving around an environment it hasnt seen before. The problem it tries to solve is to identify an abandoned backpack / luggage.*

Despite the simplicity of the problem statement this is a very challenging problem to solve. To begin with the robot must be creating static maps of the environment to be able to navigate it. Closer to the core task, we will need to preprogram the agent with all sorts of deep learning models to be able to even recognize a backpack in its perception system. Unique object ID must be assigned (symbolic segmentation) and a very accurate scene graph must also be generated by its probabilistic reasoning system. It does not stop there, the agent must be able to distinguish a situation  where the backpack that was left behind by its carrier to a companion traveler to e.g. visit the restroom from the situation where the backpack was left behind maliciously. Relational information must therefore be generated to associate objects (e.g. carriers and pieces of luggage) and such information must be stored in the KB but perhaps more importantly the agent must be able to **reason** using the stored information in the KB. 

For example, for the sentence $\beta$ that declares that the backpack was separated from the owner, we need to _entail_ a sentence $\alpha$ (and we denote it as $\alpha \models \beta$) that the backpack was handed over to $\mathtt{nobody}$ and therefore justify an action to sound the security alarm. Note the direction in notation: $\alpha$ is a stronger assertion that $\beta$. 

## Automated Reasoning Group in AWS

Logical reasoning is not only for scene analytics. AWS was the first cloud provider to recognize its significance and the following video shows why and what they have developed in this space. 

[![The Evolution of Automated Reasoning Technology](https://img.youtube.com/vi/x6wsTFnU3eY/0.jpg#center)](https://www.youtube.com/watch?v=x6wsTFnU3eY)
_AWS re:Inforce 2019: The Evolution of Automated Reasoning Technology at AWS_

Still to _learn_ the value of logical reasoning you need to go to simpler domains / worlds than scene analytics and cloud networking - world models that are simple and instructive are the way to learn. 