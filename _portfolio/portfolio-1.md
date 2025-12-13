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

Over the following weeks, we engaged in an iterative design process. 

We began by ideating a range of functions that a product in the target scope could perform, and then developed a morphology chart describing several possible functional flows.

<object data="/assets/portfolio-1-assets/function-morphology.pdf" width="1200" height="750" type='application/pdf'></object>

We then selected some of the more promising candidate solutions and developed them further.

<object data="/assets/portfolio-1-assets/function-analysis.pdf" width="1200" height="750" type='application/pdf'></object>

We shared some of our design concepts with our classmates and requested feedback.

<object data="/assets/portfolio-1-assets/me382-design-review.pdf" width="1200" height="750" type='application/pdf'></object>

![design review request](/assets/portfolio-1-assets/design-review-request.png)

![design review feedback](/assets/portfolio-1-assets/design-review-feedback.png)

The expectation for this portfolio is that we should present a clear analytical justification of our design choices. I can't do that because I don't think I chose the best design. I don't even think I chose a good design. I was exhausted and overwhelmed, so I picked designs that I knew I could model and that satisfied my tier 1 stakeholder requirements.

My chosen solution uses a lever-actuated button to handle the input of a rising helium balloon, which activates a motor that drives a linear actuator to make contact with the next module and deliver a regulated 12V voltage as an output. In order to make the design visually interesting, I used a 3d-printed two-stage reduction gear assembly to transfer power from the motor to the linear actuator.

# 3.  Detailed Design, Prototyping, and Simulation
## a. [Final Engineering Drawings](/assets/portfolio-1-assets/final-drawings.pdf)
<object data="/assets/portfolio-1-assets/final-drawings.pdf" width="1200" height="750" type='application/pdf'></object>
The final design includes 19 custom mechanical components, 17 of which are designed to use 3d printing as their primary production process. 16 are FDM and one is metal SLS.

Of the remaining two, one is designed to be prototyped on a resin printer and then injection molded, and the other is designed to be 3d printed and then sand cast in bronze.
## b. [Mechanical Simulation Video](https://1drv.ms/v/c/515053d450ede5d2/IQD6dU_WN3qYSr5FDBlTOuzgATTtWnJXm8XzXTEnI2pQe1k?e=zaewvE)
<video controls width="100%">
    <source src="https://1drv.ms/v/c/515053d450ede5d2/IQT6dU_WN3qYSr5FDBlTOuzgAaiuY21RP6GqYWiGlo-GEYI?width=2880&height=2160" type="video/mp4">
</video>

## c. [Mechatronics Schematic](/assets/portfolio-1-assets/me382-circuit-schematic.svg)
![schematic](/assets/portfolio-1-assets/me382-circuit-schematic.png)

A 4S LiPo battery powers a voltage regulator, which delivers a regulated 12V voltage to the rest of the circuit. The lever-actuated switch and each of the two pogo pins are modeled as momentary switches.

A DPST normally-open relay closes when the input switch has been pressed. This delivers power to (1) the motor and (2) the relay itself, keeping it open even if the input switch is released.

A DPDT relay switches when the output connection makes contact. This (1) turns off the motor and (2) delivers power to the relay, keeping it switched even if the output connection is broken.

## d. Mechatronics Simulation
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

## e. [Hand calculations for lever force](/assets/portfolio-1-assets/lever-calcs.pdf)
<object data="/assets/portfolio-1-assets/lever-calcs.pdf" width="1200" height="750" type='application/pdf'></object>

# 4.  Evaluation, Reflection, and Recommendations

## a. External Evaluation

I received structured feedback from stakeholders at two points during the project:

  - [Feedback from the Design Review for Convergence](/assets/portfolio-1-assets/design-review-feedback.png)
    ![Feedback from the Design Review for Convergence](/assets/portfolio-1-assets/design-review-feedback.png)
    The feedback here was surprisingly positive. The main concern was a request for more detail on the third design concept. I chose not to use that concept, and instead selected the one that got the more positive response.
  - [Feedback from the Final Review](/assets/portfolio-1-assets/final-review-feedback.png)
    ![Feedback from the Final Review](/assets/portfolio-1-assets/final-review-feedback.png)
    This feedback was also quite positive. The only critique was that the scale on the image I chose to present was unclear. I believe I've addressed that here by providing a full set of engineering drawings in addition to the glamour shots.