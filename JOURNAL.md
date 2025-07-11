---
title: "baby's First PCB"
author: "kevin"
description: "Esp32 dev board / flight controller"
created_at: "2025-05-26"
---
Total time spent: 26 hours (probably more from time spent researching pre-journal)

# May 26th: Preliminary Research

I have no idea what I'm doing, so I spent some time trying to figure that out. Decided to use KiCAD as my PCB editing software and looked up some information about how to route a USB-C port to the ESP32 microcontroller.

Spent some time actually learning how KiCAD works. No pictures, as it was mostly setup stuff today.

**Total time spent: 3h**

# May 27th: Schematic Editing

Begun the schematic today! Following the documentation, I connected a USB-C port to the esp32 microcontroller. I'm using the AMS1117 voltage regulator for now, but ive heard it isn't the best choice, so I might swap it out later. I also added data protection for the USB D+ and D- lines. Still have to integrate the gyro as well as buttons for microcontroller reset and stuff.

![image](https://github.com/user-attachments/assets/f27f9fba-0724-4900-86f3-776b7295a620)

**Total time spent: 1h**

# May 29th: Finished schematic version 1

Figured out the gyro I was going to use (MPU6050) and dug through some documentation to figure out how to connect it up. Also added boot and reset buttons as well as mounting holes and GPIO pins to the schematic.

![image](https://github.com/user-attachments/assets/5f51e6bc-17ec-4b16-9ee0-3253c81fec1e)


**Total time spent: 3h**

# May 31st: Quite a lot of routing work

Just spent a lot of time today routing the actual circuit board for the schematic. Got most of the important features done, but havent done any of the GPIO pin routing stuff yet. 

this is literally a puzzle game im gonna go crazy man

(nvm i decided to do the gpio pins, didnt take that much longer)

Also decided to post it on hack club and reddit so people can fix my many many beginner pcb routing mistakes that I dont know about yet

![image](https://github.com/user-attachments/assets/963bcb25-22d3-45dd-8f25-353ab07ea6f1)


**Total time spent: 4h**

# June 1st: I'm bad at routing

Turns out you get a lot of feedback when you post a PCB on reddit. Gonna do this now for all future projects. A bunch of the components I put in there were unneccessary apparently so I removed them, as well as fixed up the routing a bit (which quite a few people on reddit were annoyed by). I also decided to replace the AMS1117 voltage regulator because it has weird capaciator requirements and also is just outdated in general.

(this is me from the future, i forgot to take a screenshot of the pcb at this stage sorry)

**Total time spent: 3h**

# June 3rd: ahhhhhhhhhhhhhhhhhhh

well i forgot something

Turns out for this to be a flight controller, it has to be able to accept voltage from drone batteries. Drone batteries are not 5v. Therefore, I now need a buck converter module so my PCB can actually accept the power from a drone power distribution board.

My schematic did not have a buck converter. See the problem?

After a while of looking at datasheets, I settled on the TPS82130 buck converter and added it into my schematic.

<img width="912" alt="image" src="https://github.com/user-attachments/assets/aa239086-807e-4d00-961b-e150f0ef3caf" />

**Total time spent: 3h**

# June 4th: Crazy? I was crazy once.

Spent some time routing the new buck converter and made several quality of life routing improvements as well. Thankfully, I had more than enough space to fit it onto my board. 

The PCB is basically finalized now. Still a decent amount of bad practice, but if it works, it works.

<img width="769" alt="image" src="https://github.com/user-attachments/assets/5ad467d2-dfa5-44be-9b41-b017876195ec" />

**Total time spent: 2h**

# June 5th: i hate you JLCpcb

Spent a stupid amount of time fixing minor things and adjusting small stuff because JLCPCB said the things I needed were out of stock apparently. Also had to spend a bunch of time figuring out how to optimize my JLCPCB order in the first place. It costed around $100 for the PCB assembly in the end. I could probably optimize it more but had to go to sleep

basically nothing changed so no screenshot

**Total time spent: 3h**

# June 7th: blblbllblblblblbl

did some bom optimizing and got the material cost from like $125 down to like $110, most of it was due to this one gyro module I was using being insanely overpriced on jlcpcb for no reason, replaced it and did some other adjustment things as well

also added a magnetometer because apparently those are also pretty important in drone flight controllers??? didnt add to much to the cost tho

heres what the pcb looks like now

<img width="698" alt="image" src="https://github.com/user-attachments/assets/d776ad23-389e-42bd-bfb0-6f61b03f313b" />

![image](https://github.com/user-attachments/assets/d296b6aa-5438-4643-97a1-4948059aab43)


**Total time spent: 2h**

# June 8th: datasheets will be the end of me

did bom optimization
nothing changed
ahhhhhhhhhhhhhhhhhhhhhh

**Total time spent: 2h**
