---
layout: project
title: "NutCracker Deeper Analysis"
description: Statics Design Project on a nutcracker able to crack a macadamia nut
technologies: None
image: /assets/images/Nutcrackertitle2.jpg
---


As part of my statics work, I was instructed to design nutcrackers intended to be handheld, one designed to crack nuts using just human strength, and one designed to use a linear actuator. 
Using the typical design of a handheld metal nutcracker, there is a two-part system connected by a pin at the top and two sections where a nut can be placed, one with a larger hole and one with a smaller. 


However, that build was oversimplified. It was assumed that the nutcracker's handles would remain rigid despite the loads applied to the contraption. Now it is important to work out the rest of the details of the design


These details would be:

- locations of max elastic deformation
- a handle design that allows for a vertical deflection below 2% of its length
- a design that is mass efficient. 


Constraints and Input parameters:
Here is the previous design:
![Nutcracker design analysis]({{ "/assets/images/Powered_Nutcracker.png" | relative_url }}){: .inline-image-r style="width: 250px"}


Design parameters:

- $L = 44.53\ \text{mm}$
- $a = 30\ \text{mm}$
- $F_{nut} = 2178.9\ \text{N}$

Material and cross-section constraints:

- Deflection limit: $\delta_{\text{limit}} = 0.02 \times 44.53\ \text{mm} = 0.89\ \text{mm}$
- Mass efficiency

---

When it comes to the elastic deformation in the nutcracker, based on the loads, we can assume the max would be in the top lever. To simplify the problem for calculations, we can think of the top lever as a cantilever due to the bolt acting as a fixed support against rotation once the nut resists.
The loading is as shown:
![Nutcracker design analysis]({{ "/assets/images/elastic load in nutcracker.jpg" | relative_url }}){: .inline-image-r style="width: 250px"}
Based on these assumptions, we can say that the max deformation is likely to be at the free end of the lever because the actuator's force will likely be stronger and cause a greater vertical displacement. 


If we were looking to calculate this, we must use superposition, which would mean combining the deformations from both major loads.

$$
\delta_{\text{total}} = \frac{F_{\text{act}}\,L^{3}}{3 E I} - \frac{F_{\text{nut}}\,a^{2}}{6 E I} (3L - a)
$$

To satisfy the deflection limit, we require $\delta_{\text{total}} \le \delta_{\text{limit}}$. Solving for the required second moment of area gives:

$$
I \ge \frac{1}{\delta_{\text{limit}}}
\left(
  \frac{F_{\text{act}}\,L^{3}}{3 E}
  - \frac{F_{\text{nut}}\,a^{2}}{6 E} (3L - a)
\right)
$$

---

Material selection:
There are two major things to consider when it comes to material for the nutcracker: the material type and shape.


Type: We need a mass-efficient design, meaning that our material needs to have a high stiffness-to-weight ratio. This leaves us with two common metals, aluminum(6061) and steel(AISI 1018).
Aluminum is lightweight but more malleable, while steel is a lot heavier but a lot more stiff and better to take on loads. For our case, we want something that remains lightweight due to our handheld goal, as well as a small force not need excessive rigidity.
This makes our best choice, aluminum


Shape: The most mass-efficient shape would be an I beam or a rectangular tube. Some other options would include a solid rectangular lever or a U-channel, which are the two most often seen for nutcrackers. The choice behind most nutcrackers here, being solid or the U-channel, is human usability.
Those choices are the most reasonable when only thinking of using hands to push down. If the design were handheld, I would personally choose the U-channel because of its nice grip, light weight, and less harm if the load is off-center. 
This design uses a linear actuator, which widens our selection choices to include the more efficient designs, allowing us to go for a shape that is the most efficient, the I-beam. 

---

Realistic design:
In order to make this design functional we need to think about combining a lot of different ideas. The final shape of the cross section would be an I beam since it concentrated material in the flanges at the top and bottom in order to resist bending. 

Based on our calculations earlier, this is the moment of inertia constraint we have 

$$ I \le \frac{1}{\delta_{limit}} (\frac{F_{act} L^3}{3EI} - \frac{F_{nut} a^2}{6EI}(3L - a))$$

And our I beam moment of inertia is $$ I = \frac{bh^3}{12}$$

In real life the whole beam cannot be this shape reasonably. This means that the design needs the counter the non uniform bending moment. The best way to do this is to taper the end, starting with a thicker more mass efficient design near the nut and tapered near the end as it gets to the linear actuator. 

Assuming moment balance, the Force of the linear actuator at that point is about 1467N which gives us a target moment of inertia of 220mm^4 to stop the tip from dipping below .89mm

![Nutcracker design analysis]({{ "/assets/images/final_crosssection_design_nutcracker.jpg" | relative_url }}){: style="width: 100%; display: block; margin: 20px auto;"}


Usability:
- The I beam design makes it much more stiff which is important for a design that is so small
- The nutcracker is still extremely due to the power of the actuator, which makes it a little unreasonable and none of the drawings are particularly to scale. This design is merely representative of what is best for such a design. For a more realistic design that is longer and over all larger the moment of inertia would need to be much greater.
- the material is very reasonable for such a design, but if it needed to be stiffer, steel is a great option, but since the loads are very small aluminum works perfectly. 



Information on Macadamia nuts found at: 
Schrauf, C., Huber, L. & Visalberghi, E. Do capuchin monkeys use weight to select hammer tools?. Anim Cogn 11, 413–422 (2008). https://doi.org/10.1007/s10071-007-0131-2 
