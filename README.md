# Robotic Automation 
This project is the culmination of work that took place over a 3 month period in mid 2017 to develop 8 x robotic automation machines to automate a highly skilled task that was a high cost, labour intensive, difficult to manage as well as tricky to ensure constant quality. 

## Completed Machines After 3 Years Use
It is customary to start by showing completed photos of the artefact's to show how the design developed. The machines I specified, designed and built are called Adam & Eve, mainly because one takes a male insert and one receives a male insert. Also, they were the first 2 of 8 built so it felt natural to give them these names. The machines below may look a little scruffy but they have been producing 1 part every 22 seconds for the last 3 years. They significantly improved the productivity of the manufacturing cell while allowing a dataum for further improvements to be made. They are modular in design so can be quickly updated with minimal fuss and all parts have been specified with open source software and next day standard spec parts to reduce the cost and risk as much as possible. 8 of these machines (4 of each type) were built at a cost of £140k in total which is around £80k less then a single machine was quited for form automation providers. 

<p align="center"><img src="assets/AdamAndEve.jpg" width="100%"></p>


## Project Outline
The project was born from the need to improve the manufacturing output of a home Gas Regulator which required a highly skilled but intensive style of manufacturing. Components were difficult to implement within a fully automated framework due to their texture, size, orientation and supplier packing. Additionally, fully automated, even semi-automated machinery was prohibitively expensive while still allowing UK manufacturing. 

<p align="center"><img src="assets/regulator-image.jpg" width="100%"></p>

Previous attempts to automate the full assembly had failed due to high costs across managing the automated machine, long periods of downtime due to part failure as well as not offering the flexibility required when changeovers or new orders were received. 

I was asked to provide a solution to enable the manufacturing cell to increase their production rate of 55 units per hour to 110 units per hour, without any increase in staffing levels as well as providing a manufacturing cell with flexibility to either have 3/4/5 or 6 team members to enable day to day flexing of cell output.

## Ideation

The initial starting point of the project was to analyze the current processes to identify opportunities for automation as well as line balancing and task consolidation. Part of my role within the business was to develop and deploy these tools to improve processes so I was familiar with the concepts. The assembly process from raw material to tested, assembled and packaged products was 5 key steps. The 4th step required the assembly of a brass insert into the regulator body and the assembly of the hose to the regulator body. This was 1 single labor intensive task that required heavy tooling and had high PPE requirements. This task also required the manual application of Loctite glue to threaded elements of the brass insert and the hose. Both components also had specific torque requirements; the hose for example required torqueing to 60 Nm. 

<p align="center"><img src="assets/hose-brass-assembly.png" width="100%"></p>

Of the whole a build process this task (task 4) was identified as the most possible to be automated, due to its repetitive nature as well as being a key bottleneck with respects to downtime and equipment failure. Additionally, it was seen that if this process could be at least halved in terms of process time, then it would serve as a platform for future productivity benefits as other parts of the process were pulled up as future line balancing tasks were completed. 

## Development

So at this stage, the task was clear. Develop an automated system that will complete the hose to body assembly as well as the brass insert to body assembly. My initial thought was to seek external help form automation manufacturers. However, upon receipt of specification their costs come back at circa £175k-250k per machine and a 4-6 month lead time. The cost was not supported by the savings and the lead time would not support the production program so the task was then to build solutions in house. I was given full use of the site maintenance team as well as a small tool room to achieve this task. I was given 8 weeks to complete all the design, development, build and implementation of these in house machines into the line, as well as ensure relevant CE criteria was achieved. To achieve this I was given no more than £140k for the complete project - which required a full CapEx approval (2 weeks fast track). 

## Design and Build

To achieve the rapid turn around of the project I decided to split the tasks into 2 separate items and automate the key functions. I would deeply a person to transition the work between the machines and manage the positioning of stock. Depending on requirements this aspect could be automated away using CoBots such as the UR3e from [Universal Robots](https://www.universal-robots.com/products/ur3-robot/). 

### Framework

The framework of the machines was chosen to be 40mmx40mm with 8mm groove [aluminum strut](https://www.universal-robots.com/products/ur3-robot/) by RS. This strut would allow for fast assembly, I could cut it on a band saw as well as easily chamfer the edges to remove burrs. It was also very readily available and come in 8m lengths for next day delivery. The business also had an account with RS which allowed me to proceed with a build without a full CapEx approval. Additionally, as the strut would make the frame of the machine I would use the 8mm groove to install Plexiglas and provide a substructure to the unit, such as shelving for the control and embedded system. 

<p align="center"><img src="assets/ally-strut.png" width="100%"></p>

### Torque Unit

To enable the Brass and hose element to be assembled some manipulation of the part was required. This manipulation had to allow for a tight torque tolerance to be achieved but also had to be quick and record torque readings so that retrospective quality checks could be completed. This torque unit would be in constant use with circa 110 uses per hour. This would be across a 3 shift pattern meaning that a robust choice was needed as well as rapid of the shelve spares (UK based for same day delivery) if required. Additionally, this element of the build was going to be the most costly part so needed to be right. Desoutter Tools were chosen for this task with the [CVI3 Controller](https://www.desouttertools.com/tools/2/electric-assembly-systems/21/cvi3-range/210/cvi3-controllers) and [EID INline Electric Nutrunners](https://www.desouttertools.com/tools/2/electric-assembly-systems/21/cvi3-range/214/eid-inline-electric-nutrunners) chosen for the task. These tools however would need to be adapted for the task at hand and will be used in a non conventional way. 

#### CV13 Controller

The CV13 controller offered full control over the attached inline nut runner but crucially could be adapted to take a 24v input that would support an embedded system to control the unit to start, stop and provide an emergency stop facility.

<p align="center"><img src="assets/cv13-controller.jpeg" width="100%"></p>

To enable automated control of the torque unit an adaption kit is required so that the I.O pinout can be accessed. The controller itself allows each pin to be configured. To start and stop the unit. 

<p align="center"><img src="assets/cv13-controller-pinout.png" width="100%"></p>

#### EID Electric Inline Torque Driver

Although these tolls are designed to be hand held the machine was it was decided to place these units vertically and fasten them into position using a mounting place. The torque guns each had a high density spring in the end which was removed so that any vertical float was eradicated. This allowed the base of the gun to act as a floor and when the device rotated the screwed element could float free and be pulled down with the counterforce off of the spring pushing it off the nut drive element. 

<p align="center"><img src="assets/inline-nutrunner.png" width="100%"></p>

### Loctite Dispenser

A key element in the application of the Loctite glue was the quantity and the position the Loctite was required to be. This was historically a manual task that was managed via eyesight and experience alone. Additionally, Loctite was one of the most expensive consumable items within the assembly so even a small continual above specification application (i.e. costed Bill of Material or BOM) resulted in a financial impact for the product line. 

Pneumatic options for dispensing Loctite glue was not viable due to the temperature gradient experienced within the facility across winter and summer (effected the viscosity of the Loctite) the as well as the variance seen on the pneumatic system airlines (also due to cold/hot weather as the line ran across an outside area). Additionally compressed air was in use throughout the facility and depending on consumption the line pressure could be sporadic. 

With this in mind a [Loctite volumetric Compact Rotor Pump]{https://equipment.loctite.com/product/Compact-Rotor-Pump-Dispenser-4.0} was selected. The rotor pump was electric and was able to apply precision quantities of Loctite without concern for viscosity issues or pneumatic variances. A key benefit was that the volume flow could be closely controlled so when coupled with the torque drive I could achieve either a 50% or 75% or any value I required circumferential coverage - I just needed to ensure that timings were correct. As 8 machines were required 8 x off of these nits were needed which alone cost circa £34k of the £140k budget. A controller unit for each dispenser was also still required to manage the application.

<p align="center"><img src="assets/loctite-dispenser.png" width="100%"></p> 

