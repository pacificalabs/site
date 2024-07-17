---
title: "Has and Belongs To Many (Headaches)"
meta_title: ""
date: "2022-03-02"
description: "We provide tips to make the setup of HABTM associations painfree."
image: "/images/image-placeholder.png"
categories: ["Application", "Data"]
tags: ["ruby-on-rails","active-record","developer","database","back-end"]
author: "Tarun Mookhey"
draft: false
---
The HABTM association is often confusing and can lead to frustration if defined incorrectly. Here find instructions on how to set it correctly. 


### ***Why this matters:***

One of the more complicated associations.....

ActiveRecord requires you to [*define]({{< ref "has-and-belongs-to-many.md#appendix" >}} "1") the relationships between two classes.
Whilst the *has_many* and *belongs_to* association methods attract the most attention[*]({{< ref "has-and-belongs-to-many.md#1" >}} "1"), let's consider the more obscure *has_and_belongs_to_many*.

### ***Appendix***
1. *BTW Did anyone tell you that software development requires you to spend an insane amount of time thinking of the nature of things in the world and their interrelationships? All in the name of data modelling.*

2. *And let's admit, especially for beginners, newbies for those rusty on ActiveRecord Associations, we'll be tempted to try and jury-rig as many relationships into this association and make it work.* 

 
 




