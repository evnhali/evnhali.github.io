---
title: "ME382: Intro to Mechanical Engineering Design"
excerpt: "Term Project: Rube Goldberg Device Module<br/><img src='/assets/portfolio-1-assets/glamour-shot.png'>"
collection: portfolio
---

# 1.  Presenting and Justifying a Problem and its Solution Requirements
## a. Background
OSU ME382 Introduction to Mechanical Design is a project-based class where students spend 11 weeks developing and testing a solution to a problem. For Fall 2025, the assigned problem was to build a Rube Goldberg device as a class: each student was independently responsible for designing one module, which would accept input from the previous student and deliver an output to the next student. Each of us was tasked with generating our own output function for the next student to accept.

## b. Acceptance Criteria
The key requirements of the assignment were that the final design must be 3d-printable and include a mechatronic component.

## c. The House of Quality

We began our design process by performing a stakeholder analysis in the [House of Quality](https://asq.org/quality-resources/house-of-quality) format.

<object data="/assets/portfolio-1-assets/house-of-quality.pdf" width="1200" height="750" type='application/pdf'></object>

## d. Benchmarking

We also performed a benchmarking exercise where we were tasked with identifying and analyzing products with similar function. I found this confusing because I could not identify any existing products that met the minimum acceptance criteria, but [I did my best.](/assets/portfolio-1-assets/final-drawings.pdf)

I later found some excellent products on 3d printing sites that would have fit the assignment perfectly:


- [Sci-Fi Marble Run Lab](https://makerworld.com/en/models/1937432-sci-fi-marble-run-lab#profileId-2080478) by Structales:
  This design is a great demo of the potential of 3d printing for creating complex mechanical assemblies. It requires 866g of filament and 9 off-the-shelf parts costing a total of $30. Reviews are excellent; users love the detail and creativity, although there are some complaints about clearance issues and difficulty with assembly. If I'd had the time to design this, it would have scored off the charts on most of my KPIs. The main problems with it are that (1) it's a marble run and (2) it's not designed to accept the previous student's input or to generate a material output.
- [CyberExpress Train](https://makerworld.com/en/models/2040212-cyberexpress-train#profileId-2201073) by Jorge Rui
  For less than 500g of filament and $60 in parts, this model lets anyone print a working powered model train with modular tracks. It's a very new model, but early reviews are good. It's visually-interesting, computationally-tractable, and could be implemented as a predictable output. Like the marble run, it would score much better than the solution I developed; like the marble run, it's a far more complex assembly than I was prepared to design and revise multiple times in the space of a few weeks.

# 2.  Generating and Analyzing an Original Solution

# 3.  Detailed Design, Prototyping, and Simulation
## 1. [Final Engineering Drawings](/assets/portfolio-1-assets/final-drawings.pdf)
<object data="/assets/portfolio-1-assets/final-drawings.pdf" width="1200" height="750" type='application/pdf'></object>
The final design includes 19 custom mechanical components, 17 of which are designed to use 3d printing as their primary production process. 16 are FDM and one is SLS.

Of the remaining two, one is designed to be prototyped on a resin printer and then injection molded, and the other is designed to be 3d printed and then sand cast in bronze.
## 2. [Mechanical Simulation Video](https://1drv.ms/v/c/515053d450ede5d2/IQD6dU_WN3qYSr5FDBlTOuzgATTtWnJXm8XzXTEnI2pQe1k?e=zaewvE)
<video controls width="100%">
    <source src="https://1drv.ms/v/c/515053d450ede5d2/IQT6dU_WN3qYSr5FDBlTOuzgAaiuY21RP6GqYWiGlo-GEYI?width=2880&height=2160" type="video/mp4">
</video>

## 3. [Mechatronics Schematic](/assets/portfolio-1-assets/me382-circuit-schematic.svg)
![schematic](/assets/portfolio-1-assets/me382-circuit-schematic.png)

## 4. Mechatronics Simulation
### Simulation 1: Ideal Scenario
 In the ideal scenario, the input switch is triggered after 3 seconds and remains depressed for the duration of the trial. The output connection makes contact after 30 seconds and the circuit remains live indefinitely.
![Simulation 1 voltage](/assets/portfolio-1-assets/volt-sim-simple.png)
### Simulation 1 schematic:
![Simulation 1 schematic](/assets/portfolio-1-assets/me382-circuit-simulator-simple.png)
### Simulation 1 results:
![Simulation 1 current](/assets/portfolio-1-assets/current-sim-simple.png)
The results show that the motor remains powered until the output connection makes contact, then turns off and remains off, and the output remains powered indefinitely.

### Simulation 2: Worst-Case Scenario
 In the worst-case scenario, the input switch is triggered after 3 seconds, but repeatedly loses contact due to balloon movement. The output connection makes contact after 8 seconds, but then later switches off or disconnects after device 44 finishes its task, and may switch back on later.
![Simulation 2 voltage](/assets/portfolio-1-assets/volt-sim.png)
### Simulation 2 schematic:
![Simulation 2 schematic](/assets/portfolio-1-assets/ME382-circuit-simulator-worst-case.png)
### Simulation 2 results:
![Simulation 2 current](/assets/portfolio-1-assets/current-sim.png)
The results show that the motor remains powered until the output connection makes contact for the first time, then turns off and remains off. Power remains available to the output as it connects and disconnects at will. The relays work as intended to keep the connections in their expected states.

## 5. [Hand calculations for lever force](/assets/portfolio-1-assets/lever-calcs.pdf)
<object data="/assets/portfolio-1-assets/lever-calcs.pdf" width="1200" height="750" type='application/pdf'></object>

# 4.  Evaluation, Reflection, and Recommendations