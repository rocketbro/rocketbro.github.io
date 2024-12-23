---
layout: project
nav_title: "OpenLoom"
project_title: "OpenLoom"
type: "Specification"
description: "Standard for Loom Interfaces"
order: 1
permalink: /projects/openloom
---

### Project Contents
- Overview (this page)
- [Nodes](/projects/openloom/nodes/)  
- [Loom Trees](/projects/openloom/loom-trees/)

`OpenLoom Version 1.0`

<br>

### What Is A Loom Interface?
In February 2021, Laria Reynolds and Kyle McDonell published a paper entitled [Loom: LLMs Are Multiverse Generators](https://arxiv.org/abs/2102.06391). This paper introduced the concept of a *Loom Interface*, an innovative way to interact with language models versus standard chat interfaces. The authors noted that since LLMs are not deterministic in nature, it can be very powerful to allow a user to non-destructively traverse the many possible continuations of an exchange from any given point. This type of interaction creates a "tree" structure; many parallel versions of the conversation growing from the same root, with branches extending from any message that has multiple continuations.  

While the original paper focuses mainly on applications in the creative writing field, the core concept of a Loom interface has much broader implications. Loom interfaces are designed around the concept of **curation**; the user *curating* model responses as an **additional** (high-bandwidth & low-effort) mode of steering via solely composing prompts. These interfaces make it easy and intuitive to explore counterfactuals and to quickly determine how collapsed a given model is, simply by generating multiple responses to the same prompt and comparing them. A more collapsed model will tend to generate many similar responses, while a less collapsed model can offer thousands of possibilities in the many continuations it provides.

### OpenLoom
The OpenLoom project aims to create a unified standard that LLM interfaces based on the [Loom Theory](https://rocketbro.github.io/2024/11/16/loom-paper/) can implement to easily share trees between platforms. It defines shapes for loom trees (conversations) and nodes (messages), as well as example methods for traversing and interacting with the tree. 

OpenLoom files are stored in JSON format and should use the following naming convention:  

`example-file.openloom.json`  

This makes it easy to quickly identify files compatible with OpenLoom. Read the [Node](/projects/openloom/nodes) and [Loom Tree](/projects/openloom/loom-trees) pages for implementation details.
