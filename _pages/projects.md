---
layout: page
title: Projects
permalink: _pages/projects/
---

### **Master Thesis** (November 2023)
#### Title: [A VR Travel Application for Elderly People Focusing on Object Integration with Augmented Virtuality](/assets/pdfs/GeoTravel_Master_Thesis.pdf)
#### Summary: 
In this project, the advantages of Virtual Reality (VR) and Augmented Virtuality (AV)
are utilized to create an immersive travel experience for older adults. The existing Virtual
Reality travel application GeoTravel was updated to incorporate VR design guidelines for
seniors derived from current research. A realistic virtual avatar was integrated to represent
users in the virtual environment, offering better social interaction cues. 360-degree videos
with synchronized audio were utilized to achieve higher perceptual realism compared to
static 360-degree images. To simulate real-world interactions that improve the feeling of
presence, three AV objects — a water bottle, a camera, and a smartphone — are supported.
Users can manipulate these objects in the real-world and observe their corresponding virtual
counterparts performing the executed actions in the virtual environment.

#### Hardware Setup: 
- GeoTravel utilizes the Oculus Quest 2 Head-Mounted Display (HMD) and Quest Link for connection to a PC.
- External camera attached to the top of the headset is used for tracking the AV objects.
- An Android smartphone is employed to establish a connection with the PC running GeoTravel, supporting interaction with the AV smartphone.
- A custom-made microcontroller integrated with a non-functional camera employs Bluetooth Low Energy (BLE) wireless communication to establish a connection with GeoTravel. It transmits detected button presses to the system.

#### Software Setup: 
- The project runs on Unity version 2021.3.15f1 and utilizes the Oculus XR Plugin version 3.2.3.
- [Mirror](https://mirror-networking.com/) serves as the networking library, enabling support for two players to connect simultaneously over LAN.
- I developed a [Dynamic Link Library (DLL)](https://github.com/DenitsaAssova/ArucoMarkerTrackerDll) utilizing OpenCV and implemented in C++ to enable Aruco Marker detection and pose estimation for the AV objects.
- Additionally, Vuforia can serve as an alternative option to the Aruco Marker tracking.
- [Ubi-Interact](https://github.com/SandroWeber/ubi-interact), a Mixed Reality (MR) framework, facilitates the establishment of a WiFi connection between the PC running GeoTravel and the physical smartphone.
- An existing [DLL](https://github.com/adabru/BleWinrtDll) for Bluetooth Low Energy (BLE) wireless communication is utilized to interact with the AV camera.

#### AV Objects:
- The virtual objects' position and rotation are determined by the estimated pose of their physical counterparts, obtained from the respective tracking method.
- AV water bottle: I incorporated a simple 3D model of a water bottle into Unity and used a liquid shader to simulate water inside it. The virtual liquid follows the movement of the physical water bottle.
- AV camera: Button presses from the non-functional physical camera are transmitted to Unity, triggering the virtual camera to capture pictures of the virtual environment.
- AV smartphone: The physical Android smartphone runs an application similar to the one displayed on the virtual smartphone. When players press an icon on the physical smartphone, an event is sent to Unity, and the virtual smartphone reacts to it. 
Similar to the AV camera, the AV smartphone supports taking pictures within the VE and also browsing through them inside a gallery.

#### Videos:
- To observe a part of the virtual environment from GeoTravel, which I worked on, along with the AV camera, please watch the following [video](/assets/videos/AVCamera.mp4).
- To see the AV smartphone in action, please watch the following [video](/assets/videos/AVSmartphone.mp4).
- To view the AV bottle, please watch the following [video](/assets/videos/AVBottle.mp4).

#### Source:
Since the project wasn't entirely developed by me, please reach out to me for further details.
The source code of the Aruco Marker Tracker DLL can be accessed via the following [link](https://github.com/DenitsaAssova/ArucoMarkerTrackerDll).

### **Prop Clash** (February 2023)
#### Summary:  
"Prop Clash" is a 3D prop-hunt multiplayer game, 
created by our team of four during the practical course "Computer Games Laboratory" at the Technical University of Munich in the Winter Semester of 2023.
It embraces the theme of "Duplicate" and draws inspiration from games such as [Midnight Ghost Hunt](https://midnightghosthunt.com/) and [COD Mobile](https://www.callofduty.com/mobile). 
In the game, players can choose between two teams: Hunters and Props, and there are two game modes: Score and Round. 
Props have the ability to camouflage themselves as objects within the environment, while Hunters must locate and eliminate them. 
Props can also deploy decoys, which are duplicates of themselves, to confuse Hunters.
In Score mode, Props earn points for remaining undetected and respawn if killed by Hunters. 
Hunters score points by killing Props but lose points for killing decoys. The team with the highest score prevails.
In Round mode, Props do not respawn if killed. Their objective is to have at least one team member stay hidden until the round's end to secure victory. 
Props can use stun abilities to evade Hunters. Conversely, Hunters aim to eliminate all Props to win the round. 
Teams swap roles after each round, and the team with the most round wins ultimately claims victory.

#### My responsibilities:
- Implementing the multiplayer functionality: The game employs Unity's [Netcode for GameObjects](https://unity.com/products/netcode) for networking functionality. A dedicated host is responsible for managing the game session, 
allowing clients to connect to it using the host's IP address. At present, the game only supports LAN connections.  Within the ongoing game session's lobby, players are able to choose their team and the preferred game mode. 
The status of team selections and the votes for game modes are visible to all connected players. Essential game information, such as the round timer, players' actions, and sound effects, is synchronized throughout each game round.
- Developing the player controller: 
	- Both Hunters and Props share common abilities such as walking, running, and jumping. Additionally, for the Hunter, walking and running animations are synchronised across all players.
	- Hunters have a first-person point of view (POV) and a close-range attack. In Round mode, Hunters can be stunned by Props for a duration, rendering them unable to move or attack. This state is indicated by a visible camera shake effect.
	- Props utilize a third-person point of view (POV) and have the ability to switch between this view and an orbit camera. Both camera perspectives can be zoomed in and out as needed. In Round mode, Props can stun Hunters.

#### Source:
Build version of the game can be found at the following [link](https://denito10.itch.io/prop-clash).
Since the project wasn't entirely developed by me, please reach out to me for further details.

#### Trailer:
Watch the trailer for "Prop Clash": [![link](/assets/images/propclash.jpg)](/assets/videos/Trailer.mp4).


### **Gravity Overrider** (June 2022)
#### Summary: 
"Gravity Overrider" is a single-player 2D platformer game developed by our team of three for the [Semester Game Jam](https://semestergamejam.de/en/home/) during the Summer Semester of 2022. The theme of the Game Jam was "Override".
In the game, players assume the role of an astronaut exploring space with a weapon that changes colour and the ability to control gravity. 
As players traverse the environment, they encounter enemies and orbs of various colours, as well as hazardous fire obstacles.
Players must shoot the enemies or evade them, collect the orbs or leap past them, but the deadly fire hazards must be avoided by strategically manipulating gravity.
Under normal gravity, players should only eliminate enemies and collect orbs that match the colour of their weapon to accumulate points. Touching an enemy results in the loss of a life. 
Additionally, firing at or touching incorrect enemies or orbs leads to a deduction in points.
In reverse gravity, the rules are inverted – the colour of the shot enemies and collected orbs should be different from the weapon's colour. Touching a fire barrier results in the loss of a life. The game ends once all lives are lost.

#### My responsibilities:
With only two days to complete the game, our team collaborated closely on nearly every aspect of the game development. 
My primary responsibilities involved generating the environment and creating the tutorial.

#### Source:
Build version of the game can be found at the following [link](https://shayyn20.itch.io/gravity-overrider).
Since the project wasn't entirely developed by me, please reach out to me for further details.


### **Anubis' Trial** (June 2022)
#### Summary:  
"Anubis' Trial" is a 3D rogue-like survival single-player game with puzzles, 
created by our team of four during the practical course "Computer Games Laboratory" at the Technical University of Munich in the Summer Semester of 2022.
It embraces the theme of "Reflection" and draws inspiration from ancient Egyptian mythologies. 
Each level involves navigating a procedurally generated maze while uncovering hidden segments of a mirror. 
To retrieve these segments, players must engage in combat with various enemies using their unique abilities. 
Upon gathering all mirror segments and successfully solving a reflection puzzle, players face a more formidable opponent. 
In the final level, they initiate the "Guardian of the Scales" test and must overcome their own dark reflection. 
Victory in this trial leads to ascension to heaven, while defeat results in the loss of one's soul.

#### My responsibilities:
- Integrating the Enemy AI into the game: 
Within the maze, players will encounter three distinct types of enemies: a stationary snake that bites, a mummy skilled in close combat with two light and one heavy attack, 
and a spider capable of long-range shooting with three varieties of poison. 
Following the completion of a level, players confront a mini-boss equipped with five unique attacks. 
This formidable foe relentlessly pursues them, and as its health diminishes, it enters a one-time brief recharging phase where it becomes invulnerable to harm. 
During this phase, it summons in-maze enemies to aid in its defense.
The final boss takes on a dark incarnation of the player themselves, wielding the same weapons and attacks. 
Additionally, it possesses the ability to summon a shield that provides protection from all attacks and enables it to regenerate health.
- Creating and rigging models for some of the enemies

#### Source:
The source code of the project can be accessed via the following [link](https://drive.google.com/file/d/1TtsZsHTA6P_689QgJsLTLyVcAz0i-vpI/view?usp=sharing).
Build version of the game can be found at the following [link](https://shayyn20.itch.io/anubis-trial).

#### Trailer:
Watch the trailer for "Anubis' Trial":[![link](/assets/images/anubistrial.jpg)](https://www.youtube.com/watch?v=p1tf53QCS6Q).

### **SMPL: A Skinned Multi-Person Linear Model** (February 2021)
#### Summary: 
This project offers a C++ implementation of the SMPL (Skinned Multi-Person Linear) model. SMPL was introduced by researchers at the Max Planck Institute for Intelligent Systems ([SMPL.pdf](https://files.is.tue.mpg.de/black/papers/SMPL2015.pdf)). 
It represents human bodies as a simplified mesh structure composed of vertices. 
This model can accurately capture different body shapes and poses. To achieve this, SMPL utilizes beta and theta parameters as input. 
The beta parameters represent the coefficients that determine the shape of the body. By adjusting these parameters, you can generate different body shapes, such as slim, muscular, or obese, within the model. 
The theta parameters define the rotation of each joint in the body, allowing the model to be posed in different configurations. Adjusting theta parameters changes the pose of the body, enabling it to take various positions and movements.
SMPL is widely used in computer graphics, animation, and other fields where realistic human body representation is required. 

#### Source:
The project can be accessed via the following [repository](https://github.com/DenitsaAssova/SMPL).

<!--#### Results:
The images below illustrate several outcomes following adjustments to the beta and theta parameters.
![](/assets/images/smpl1.png){: style="display: inline-block; width: 45%; height: 500px;"}
![](/assets/images/smpl2.png){: style="display: inline-block; width: 45%; height: 500px; margin-left: 10px;"}
-->


### **Bachelor Thesis** (August 2021)
#### Title: [An AR Serious Game about Obsessive-Compulsive Disorder](/assets/pdfs/An_AR_Serious_Game_about_Obsessive_Compulsive_Disorder.pdf)
#### Summary:
Obsessive-compulsive disorder (OCD), affecting 2.3% of the population, often goes untreated due to stigma and a shortage of therapists. To address this, self-help techniques like serious games have emerged. Despite its prevalence, misconceptions about OCD persist, highlighting the need for awareness and education.
This project introduces an Augmented Reality Serious Game targeting OCD, integrating self-help techniques and an educational component. Drawing from the analysis of scientific papers and existing applications, the AR game was developed and evaluated by both healthy individuals and OCD patients. Initial feedback is positive, but further extensive research is necessary for a comprehensive assessment.

#### Source:
##### [AR Foundation Variant](https://github.com/DenitsaAssova/AnARSerioisGameForOCD)
This is the primary version of the game, built and deployed for iOS and Android using AR Foundation. It includes all three mini-games.
##### [Vuforia Variant](https://github.com/DenitsaAssova/AROCDCleaningLevel)
This project features a revised version of the cleaning level that utilizes Vuforia and a pretrained Convolutional Neural Network (CNN) for detecting and tracking objects contaminated with bacteria.


