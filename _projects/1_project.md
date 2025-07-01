---
layout: page
title: Simulation of the 2D Flow and Kármán Vortex Street Behind a Rectangular Cylinder
description: with background image
img: assets/img/project01_main.jpg
importance: 1
category: work
related_publications: true
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project01_main.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

<h2>Documentation</h2>
Dimensions 
Grid: 481 × 241 + 1 ghost node on the right
Grid size: 4 m × 2 m 
Cylinder size: .7 m  × .7 m 
Cylinder distance: .7 m away from top, bottom, left walls (exactly in the middle) 

Time steps
Total time: 5000 s
Time increment (dt): .5 s 
Output frequency: every 20 time step

Constants 
Re = 100 //Reynold's number
L = .7 m //Characteristic length 
dynamic viscosity = 1.46e-5 m^2/s //dynamic viscocity of air
U = Re*viscosity/L //inlet speed

Tolerance for the Poisson solver: 1e-11

Boundary Conditions
Inlet (left wall):  	0,j= -dy*U*(j-j_0) where j_0 is the middle node in y (so every -∂∂y= U)
	𝜁 = 0 
Outlet (right wall): set ghost nodes to  i = 2* i-1- i-2 (sets the second derivative to 0)
		        set ghost nodes to   𝜁i = 2*  𝜁i-1-  𝜁i-2	
Top/bottom walls: -,0=0,0=-0,j (Equal to the inlet condition values) 
	𝜁 = 0
Cylinder walls: 	 = 0
	𝜁 = 2d2*adjacent (d = Δx = Δy) (no slip boundary condition)
	𝜁corner = ∇2
Inside the cylinder: ψ= 0
		         𝜁 = 0

<a class="citation" href="#HirotaM1965Numerical">(Einstein &amp;Taub, 1950)</a>
{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
