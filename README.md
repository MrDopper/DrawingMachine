# CNC Drawing Machine | Arduino + GRBL

**A desktop pen plotter that connects mechanical motion, G-code, and computer-based control.**

**Project type:** Personal robotics / automation project  
**Build period:** Approximately three weeks  
**Status:** Working prototype; software workflow improvements in progress for Steamoji

## Demo

**[▶ Watch the CNC drawing machine demonstration](https://youtu.be/urHR4juFkFs)**

*The demonstration shows the current machine. Add a short caption specifying the drawing, control method, and what was tested.*

## Why I built it

I built this CNC drawing machine to explore how software instructions become physical movement and to make real-world automation more approachable for students. The project combines mechanical assembly, an Arduino-based motion controller, G-code, and a browser-based control workflow.

Also, I developed the prototype with Steamoji Richmond Central, a STEM learning academy, in mind. After completing the initial build in approximately two weeks, I presented the machine and a proposed curriculum to academy management as a potential product for hands-on STEM activities.
The machine and educational package were proposed for sale; this repository does not represent a completed purchase, installation, or classroom deployment by Steamoji.
What motivated me was not only building the machine itself, but the opportunity to help students learn how to work with real life problem. 

For me, the most valuable part of this build was **integrating hardware and software, diagnosing problems, and turning a prototype into a system someone else could understand and operate.**

## System overview

```text
G-code file
    |
    v
ChiliPeppr (browser-based control interface)
    |
    v
Serial Port JSON Server (USB serial connection)
    |
    v
Arduino + GRBL-compatible controller
    |
    v
Stepper-driven X/Y motion -> Drawing tool
```

I have also been investigating an **Inkscape vector-to-G-code workflow**. Simple geometry and complex traced images do not always export the same way; reliable conversion of detailed traced images is still a work in progress.

## Hardware and software

| Area | Components / tools |
| --- | --- |
| Motion system | CNC drawing-machine frame and stepper-driven axes |
| Controller | Arduino running a GRBL-based motion-control setup |
| Machine instructions | G-code |
| Control interface | ChiliPeppr (GRBL workspace) |
| Serial communication | Serial Port JSON Server over USB; tested at 115200 baud |
| Design workflow | Inkscape; image tracing and G-code extension compatibility under investigation |
| Development environment | macOS |

## What I contributed

- **Hardware integration:** Assembled the machine and connected the motion-control hardware with the controller.
- **Controller setup:** Configured and troubleshot communication between the Arduino/GRBL system and a computer-based control interface.
- **Software troubleshooting:** Investigated vector-path preparation, G-code export, and compatibility issues with an older Inkscape extension.
- **Application design:** Explored how the machine could support hands-on teaching about G-code, machining concepts, and computer-controlled movement.

## Current limitations and next steps

- Improve the reliability of the **Inkscape -> G-code** workflow, especially for traced images with many nodes.
- Document machine calibration, repeatability tests, common errors, and how they were resolved.

