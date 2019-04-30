# Fluid Simulation via the Affine Particle-in-Cell Method

## Table of Contents

Proposal
Milestone


# Milestone

## Accomplishments

So far, most of our effort has gone into the implementation of a 2D APIC simulation via Stanford CS348C. We've implemented the key grid and particle momentum transfer equations that are particular to the APIC implementation. The equations are as follows:

![alt text](https://github.com/alishelton/184-project-proposal/blob/master/imgs/eq13.png)
![alt text](https://github.com/alishelton/184-project-proposal/blob/master/imgs/eq14.png)

We are currently working on generalizing the code to 3D particle simulation, and from there will move on to surfacing the particle clouds. We have also started work on an OpenGL simulator for running our 3D simulations, as our current simulator is restricted to 2 dimensions. 

## Preliminary Results

Below is a comparison of a PIC (Particle-in-Cell) and our APIC simulation:

(gifs here)

## Progress by Plan

In terms of our initial planning, we had hoped to have a completed PIC and APIC implementation by the end of the second week. Since we are currently using a sample of starter code, a PIC implentation was provided, and we can readily compare that against our APIC implementation. Since the implementation is in 2D however, we are a bit behind. We are also a behind on schedule in terms of the simulator, however we hope to have that running as soon as possible to for testing our 3D generalization of the APIC aglorithm. 

## Planning Updates

### Week 1 (Done)

-2D PIC and APIC understanding

### Week 2 (Nearly Done)

- complete APIC implementation
- beginning of a 3D simulation environment

### Week 3

- APIC 3D generlization
- complete 3D simulation environment
- beginning implementation of surface mesh algorithm

### Week 4

- finished implementation of surface mesh algorithm and surace rendering
- final report + optimizations

## Resources

- http://graphics.stanford.edu/courses/cs348c/PA3_APIC2017/index.html
- http://alexey.stomakhin.com/research/siggraph2015_apic.pdf
- http://rlguy.com/gridfluidsim/
- https://github.com/austinEng/WebGL-PIC-FLIP-Fluid/tree/master/demo/shaders
- http://www.thevisualroom.com/marker_and_cell_method.html
- http://plaza.ufl.edu/ebrackear/

# Proposal

## Summary

We intend to design a fluid simulator based on the affine particle-in-cell method. To ensure realism of the simulations, we also intend to render the fluid point-clouds via surface splatting techniques. 

## Team

Alex Fang, Ali Shelton, Raymond Ly

## Problem

Fluid simulation is an active field of research, and developing fluids with realistic physical properties is useful in applications ranging from reasearch into complex ecological systems via simulation to the beautification of contemporary gaming. High fidelity physical properties can be especially important in research, where the results are often dependent on the assumption that the simulation is faithful to some degree to the real scene. The challenge in designing such a simulation methods comes from faithfully representing such a fluid to retain its physical properties without introducing excessive assumptions or noise. 

To provide such a simulation, we turn to the APIC (Affine Particle-in-Cell) method, which builds on the PIC (Particle-in-Cell) and FLIP (Fluid-Implicit Particle) methods to produce a provably more stable simulation that has much lower energy dissipation between steps.

## Goals and Deliverables

### Planned Deliverables

#### Goals

The overall goal of this project can be split into several stages. The first is to provide a realistic particle-based simulation of fluid motion. This includes both the correct physical implementation of the necessary primitives and visualization. The second stage is to provide a realistic texturing to the simulation by generating a surface mesh for each particle update frame and rendering this with the necessary BSDF. Given the information presented in the original [paper](http://alexey.stomakhin.com/research/siggraph2015_apic.pdf) on APIC, we can design and implement such a system with good general direction.  

Our current plan is to make use of the equations presented in the referenced APIC paper, those in the surface splatting paper, and preset BSDFs in blender to implement the simulator. 

#### Reporting

In order to report our deliverables, we will generate a number of small video clips/GIFs of our rendered fluid simulation that will reflect the simulation's key properties (conservation of energy, stability, etc.)

Clips should look similar to the below format direclty from the original [paper](http://alexey.stomakhin.com/research/siggraph2015_apic.pdf)

![alt text](https://j.gifs.com/QnkEB5.gif "APIC Vorticity")

#### Performance

In simulation systems, performance determines much of what is feasible to produce given our time constraints, and so in order to measure performance in the first stages, we will present graphs designating the time it takes to fully calculate a single simulation step at the particle/grid level. In the second stage, our performance measure are based heavily on the time necessary to produce a sufrace mesh, and then the time to render this mesh with the proper BSDF. We will also provide a graph for speedup analysis of surface mesh production time along with a written analysis of the rendering speedup over the course of the project for any different methods we attempt. 

### Hopeful Deliverables

If time permits, it would be interesting to make the system completely interactive via the project website. We may also include a number of different materials (beyond water) such as ice cream and lava, like those presented in the presentation video for the relevant paper.

## Schedule

Tasks are organized by week

### Week 1

- particle simulation system visualization via OpenGL
- rudimentary PIC (Particle-in-Cell) implementation

### Week 2

- complete APIC implementation
- surface mesh production algorithm implementation

### Week 3

- APIC optimizations
- surface mesh rendering complete/optimizations

### Week 4

- Final report + optimizations

## Resources

### Papers

- http://alexey.stomakhin.com/research/siggraph2015_apic.pdf
- http://mmacklin.com/pbf_sig_preprint.pdf
- https://graphics.uni-bielefeld.de/publications/pbg05.pdf
- https://www.cc.gatech.edu/~turk/my_papers/sph_surfaces.pdf

### Books

- https://developer.nvidia.com/gpugems/GPUGems/gpugems_part01.html

### Computing Platform/Hardware

- RTX 2070 
- Radeon RX 480 

### Software

- OpenGL
- Blender
