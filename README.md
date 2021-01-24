# Robotic Automation 
This project is the culmination of work that took place over a 3 month period in mid 2017 to develop 8 x robotic automation machines to automate a highly skilled task that was a high cost, labour intensive, difficult to manage as well as tricky to ensure constant quality. 


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

## Design

To achieve the rapid turn around of the project I decided to split the tasks into 2 separate items and automate the key functions. I would deeply a person to transition the work between the machines and manage the positioning of stock. Depending on requirements this aspect could be automated away using CoBots such as the UR3e from [Universal Robots]https://www.universal-robots.com/products/ur3-robot/. 

### Framework

The framework of the machines was chosen to be 40mmx40mm with 8mm groove [aluminum strut]https://www.universal-robots.com/products/ur3-robot/ by RS. This strut would allow for fast assembly, I could cut it on a band saw as well as easily chamfer the edges to remove burrs. It was also very readily available and come in 8m lengths for next day delivery. The business also had an account with RS which allowed me to proceed with a build without a full CapEx approval. Additionally, as the strut would make the frame of the machine I would use the 8mm groove to install Plexiglas and provide a substructure to the unit, such as shelving for the control and embedded system. 

<p align="center"><img src="assets/ally-strut.png" width="100%"></p>
