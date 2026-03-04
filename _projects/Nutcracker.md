---
layout: project
title: NutCracker
description: Statics Design Project on a nutcracker able to crack a macadamia nut
technologies: None
image: /assets/images/Lets make a nutcracker.jpg
---

As part of my statics work I was instructed to design a nutcracker intended to be hand held, one designed to crack nuts using just human strength and one designed to use a linear actuator. 

Using the typical design of a handheld metal nutcracker, there is a two part system connected by a pin a the top and two sections where a nut can be placed, one larger hole and one smaller. 

Constraints and Input parameters:
The typical hardness of a macadamia nut is 222.18kg (+/-) 18.54kg and the average diameter is 25mm. The average human grip strength is 300N.

This is how I solved the problem:

The big idea here is to get a mechanical advantage using the length of the nutcracker. 
The equation to keep in mind is F_load * d_effort = F_Load * d_load
Now the force from the nut is approximately 2178.9N giving us a required mechanical advantage of at least 7.26.

![Nutcracker design analysis]({{ "/assets/images/Nutcracker_design_one.jpg" | relative_url }}){: .inline-image-r style="width: 300px"}

Now if the nut is 3cm or 30mm from the hinge of the nutcracker, then our nutcrackers length would have to be at least 217.8mm for this mechanical advantage. This would be the minimum value, meaning the optimal is above this value. 

This minimum would give us a grip span of 181.7mm. Now here lies our issue. The optimal grip for human hand is from 45mm to 60mm. This is over double that, creating a situation where the nutcracker would have to be used by both hands for most. This calculation is also considering the idea of using the first hole to crack the nut. While this isn't the worst problem to have it is not ideal. That is where the second design came to mind.  


Powered Nutcracker:

Now the challenge here was to design a nutcracker that is able to crack itself, and the best bet for this is a linear actuator. 

The linear actuator I decided to go with based on the force, stroke, and price is the Mini Industrial Actuator with optional feedback model PA-09 from Progressive Automations. This model has a stroke of 2-40 inches, a force of 330lbs and would be crushing nuts in seconds.

Now our necessary mechanical advantage would now be 1.484 makeing this nutcracker small but mighty. Sticking to our original 30mm we would now get a new minimum distance from the hinge to be 44.53mm. Using a ratio formula using the diameter of the nut and the ratio between the lengths we get a width of 37.11mm. 

![Nutcracker design analysis]({{ "/assets/images/Powered_Nutcracker.png" | relative_url }}){: .inline-image-r style="width: 250px"}

This design is incredibly small, powerful, and to some degree unnecessary. It is possible to have a less powerful linear actuator, but it is nice to have such a fast machine. As for its actual usabilty it must be connected to a base that not only holds the actuator but the nutcracker itself, making it more reasonable to just use the handheld.




Information on Macadamia nuts found at: 
Schrauf, C., Huber, L. & Visalberghi, E. Do capuchin monkeys use weight to select hammer tools?. Anim Cogn 11, 413–422 (2008). https://doi.org/10.1007/s10071-007-0131-2