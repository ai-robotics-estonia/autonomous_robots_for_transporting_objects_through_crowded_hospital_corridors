*This is a template repository for this organization. Start by replacing the placeholder for the project name with it's actual title.*

# [Project Name]

## Summary
*This section is to be filled out by the project manager based on the [summary document](https://docs.google.com/spreadsheets/d/12xi2yOMm-X5PEecgyRe3WEurcSaN9A5z4DHgBacQT6M).*

| Company | [Company](https://website.link) |
| :--- | :--- |
| Project Manager | [Project Manager](https://profile.link) |
| Project Team | [Team Member 1](https://profile.link); [Team Member 2](https://profile.link); ... |
| Challenge Tackled |  |
| Technology Used |  |
| Lessons Learned |  |
| Result Published |  |
| Target Group |  |
| Diagrams/Photos |  |
| Video |  |

## Implementation Details

Figure below shows the architecture of our deployed system. The setup consists of
* robots
* automated doors
* user interface devices, such as tablets
* dispensers and ingestors, which are used to place and retrieve objects from the robot respectively
* and RMF, orchestrating the whole setup. 

All devices are connected via Virtual Private Network (VPN). FreeFleet is used as the fleet manager. Structurally FreeFleet is segregated to a central server and clients, a client per each robot. The server is responsible for mediating navigation requests from RMF and providing feedback to RMF via aggregating the state of the whole fleet. The FreeFleet client passes navigation requests from the server to the driver of the local robot (ROS Navigation) and provides feedback of the robot’s state. Both RMF and the FreeFleet server are running on a dedicated PC. FreeFleet server and clients communicate purely via Cyclone DDS, thus the server can simultaneously manage both ROS1 and ROS2 based robots. Each door, dispenser and ingestor is equipped with a custom controller ([door controller](https://github.com/project-covsg24/card_swipe_py); [tablet-based dispenser](https://github.com/project-covsg24/rmf_dispenser_ingestor_tools)) that accepts commands from and sends feedback to RMF. Finally, RMF Web is utilized as a graphical user interface, mostly deployed on tablets via a web browser.

<p align="center">
  <img src="https://github.com/scafld/covsg24_fleet_backend/blob/main/docs/system_setup.png" class="center" width=600"/>
</p>

For further details, refer to [our article published at the Frontiers in Robotics and AI](http://doi.org/10.3389/frobt.2022.922835) and [the replication package](https://doi.org/10.5281/zenodo.6467038). The latest source code and instructions of our ongoing development can be found in the [GitHub for SCAFLD](https://github.com/scafld). 

### Description

- *What your application does,*
- *Why you used the technologies you used,*
- *Some of the challenges you faced and features you hope to implement in the future.*

### How to Install & Run

*Provide a step-by-step description of how to get the development environment set and running.*

### How to Use

*Provide instructions and examples so users/contributors can use the project.*

### Credits

*If you followed tutorials or referenced a certain material that might help the user to build this particular project, include links to those here.*

### Licensing

*Point out your software license. In case this is something different than an MIT license, explain why.*

[MIT License](/LICENSE)

### How to Contribute

*Add guidelines to let other developers know how they can contribute to your project.*

### Testing

*Provide code examples and how to run tests for your project.*
