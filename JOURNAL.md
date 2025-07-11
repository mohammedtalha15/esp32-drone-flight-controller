---
title: "ESP32 Drone Flight Controller"
author: "Mohammed Talha (mohammedtalha15)"
description: "An ESP32-based custom PCB flight controller for drones. It has onboard gyro, accelerometer, and buck converter to step down 14.8V LiPo battery to 5V for ESP32 + peripherals."
created_at: "2025-06-10"
total_time_hours: 26
---
## June 10 – Getting Started (3h)

I didn’t know much about making a PCB at the start, so I spent a few hours researching how to begin. After checking out multiple tools, I decided to go with **KiCad**. I also read up on how USB-C ports are routed to the ESP32. 

Most of the time was spent setting up KiCad, learning the basics, and preparing for the actual schematic.
![image](https://github.com/user-attachments/assets/f27f9fba-0724-4900-86f3-776b7295a620)

**Total time spent: 1h**

## June 11 – Schematic Work Begins (1h)

Started working on the schematic in KiCad. I connected the **USB-C port** to the ESP32 and added an **AMS1117 voltage regulator**. I also included ESD protection for the D+ and D- lines. Still had to add the **MPU6050 gyro** and reset/boot buttons.
![image](https://github.com/user-attachments/assets/5f51e6bc-17ec-4b16-9ee0-3253c81fec1e)


## June 13 – Completed First Schematic Draft (3h)

Finalized the schematic with:
- MPU6050 gyro
- Reset & boot buttons
- Mounting holes
- GPIO headers

I dug through a bunch of datasheets and connection guides to make sure the components were connected correctly.

![image](https://github.com/user-attachments/assets/963bcb25-22d3-45dd-8f25-353ab07ea6f1)


## June 15 – Routing the PCB (4h)

Started routing the PCB layout. Took a while to figure out the traces, especially for power and USB lines. GPIO pins took extra time, but I finished routing them too.

Posted my progress in **Hack Club** and **Reddit** to get feedback since this is my first PCB project. People gave solid suggestions.

After all that Reddit feedback, I made some big changes:
- Removed unnecessary parts.
- Improved trace routing.
- Swapped out the AMS1117 for a better voltage regulator.
<img width="912" alt="image" src="https://github.com/user-attachments/assets/aa239086-807e-4d00-961b-e150f0ef3caf" />


## June 20 – Realized Power Issue (3h)

I realized something critical: drone batteries aren’t 5V. I needed a **buck converter** to bring the voltage down from ~14.8V to 5V. 

After a ton of research, I went with the **TPS82130**. Added that into the schematic and made space for it on the board.

<img width="769" alt="image" src="https://github.com/user-attachments/assets/5ad467d2-dfa5-44be-9b41-b017876195ec" />

## June 22 – Routing the Buck Converter (2h)

Added the buck converter to the PCB layout. Routing was smoother than I thought, and I still had space left. Did some cleanup across the PCB and finalized the layout.

**Total time spent: 3h**

## June 25 – JLCPCB Issues (3h)

JLCPCB gave me component availability issues. I had to go back and forth fixing the BOM and matching values. Adjusted footprints, reordered some nets, and optimized the board for ordering.

Didn’t change anything visibly major, but this step took a while.
<img width="698" alt="image" src="https://github.com/user-attachments/assets/d776ad23-389e-42bd-bfb0-6f61b03f313b" />

![image](https://github.com/user-attachments/assets/d296b6aa-5438-4643-97a1-4948059aab43)


## July 2 – BOM Cost Fix + Magnetometer (2h)

Some parts in the BOM were overpriced, especially the gyro. Replaced it with a more affordable version. Also added a **magnetometer** for better drone orientation accuracy.

Final board is looking great now.

## July 8 – Final BOM Optimization (2h)

Did a final review of the BOM. Compared different vendors and datasheets to squeeze out extra savings. Cleaned up part names and pricing so the board is ready for submission.

---

**Total Time: 26 hours**

This was my first time building a PCB from scratch for a real use-case. I learned a lot about hardware design, power management, and how drone electronics work. Super thankful to Hack Club for giving me the reason (and push) to try something this advanced.
