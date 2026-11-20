# zeOS - Space Invaders

Laboratory work for [Sistemas Operativos Avanzados (SOA)](https://docencia.ac.upc.edu/FIB/grau/SOA/) at the Barcelona School of Informatics, University Polytechnic of Catalonia [(FIB-UPC)](https://www.fib.upc.edu/es).


##  Project: Space Invaders on a custom OS kernel
![Space Invaders en ZeOS](demo.gif)

Final project grade: 10/10

The game runs in user mode on top of the kernel features implemented in the lab: system calls, interrupt handling and process management. It uses two processes that communicate through a shared memory page:
- **Parent (engine + renderer):** runs the game logic and draws each frame, writing only the characters that changed to reduce flicker.
- **Child (controller):** reads the keyboard and writes the ship position and input events to the shared page.


## Requirements
 
- **OS:** Ubuntu 22.04 (also tested on 24.04)
- **Compiler:** GCC
- **Emulator:** [Bochs 2.6.7](https://bochs.sourceforge.io/)


## Usage
 
```bash
git clone https://github.com/lucia-pcap/zeOS-Space-Invaders.git
cd zeOS-Space-Invaders/Milestones/M7-8
make        # build the ZeOS image
make emul   # boot ZeOS in Bochs and start the game
```
 
### Controls
 
| Key | Action |
|---|---|
| `a` / `d` | Move left / right |
| `w` / `space` | Shoot |
| `r` | Restart |
| `q` | Quit |
 
Each alien is worth 10 points, and clearing a wave gives a 50-point bonus. Every new wave makes the aliens move faster. The game ends when the aliens reach your ship.


## Lab: building ZeOS

Design and implementation of ZeOS, starting from a minimal base code:
 
- **Deliverable 1:** system calls and interrupt handling.
- **Deliverable 2:** data structures and scheduling algorithms for process management in a multiprocess system.
- **Final project:** Space Invaders, built on top of the previous deliverables.


## Repository structure
 
| Folder | Content |
|---|---|
| `Laboratory/` | ZeOS deliverables 1 and 2 |
| `Milestones/` | Space Invaders on ZeOS (final project) |
