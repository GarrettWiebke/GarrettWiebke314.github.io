---
title: Reflection
---

## Review of Module's Success

EGR 314 Embedded Systems Design 2 is an extremely difficult yet rewarding course that you learn greatly from; unfortunately, failure is one of the most common mediums for learning in this course. Here's what I did successfully and what I did not do so successfully. The module supported surface mount ESP32 startup and boot loader instantly with no issues and had full capability of its buttons, and LED uses for testing and debugging, which were all surface mount components. The power regulators' EN pin was tied to ground and, therefore, was never actually switching. The pin needed to be bent upwards so it wasn't touching the pad, and cut into a trace between the resistance divider. There was also a current draw issue with the motor driver, which led to a daughter board being needed for another component, and the connections tied to the headers I had on the PCB. 

## Module start-up tips

1. Only solder specific sections based on function first and test profusely before moving on, for example, first would be your power regulator, then your ESP, and so on. Do not solder everything at once and expect it to work.
2. After soldering any component, do a continuity test with a multimeter to make sure your connections are good and that there is no bridging that could short or fry any of your components.
3. Make sure you have the necessary BOOT and EN buttons tied to the correct pins for the ESP32
4. Make headers as much as you can, ideally every unconnected pin should be a header for robust functionality
5. Make sure 3v3 and ground aren't bridged in any capacity, the pins are right next to each other, and it is easy to do so. We've lost a lot of ESPs due to that issue 

## Lessons Learned

1. Go through the datasheet more than once and match it to your schematic many times to ensure you have the correct connections
2. Make as many headers as you can, as they can save your entire design.
3. The microcontroller is the brain of your whole subsystem and is the most important thing to care for and to get working
4. ESD protection is no joke for the ESP32. Make sure you have filtering capacitors, and be careful with your PCB itself.
5. You can do a surprising number of things to fix a PCB, although it might not be the prettiest. Never give up because nine times out of ten, an issue can be fixed relatively easily on a PCB
6. Every time you make a change to your subsystem, go over the other parts and make sure it will not conflict with them
7. Team communication is everything; help your team and work with them.
8. Adjustable power regulators require a fair bit more setup than fixed power regulators
9. For your first iteration of a design, the simpler the better, then build upon that when you confirm it's working
10. Work with the teaching team and use the resources available to you to their fullest extent 

## Recommendations for Future Students

1. Please make sure you triple, no quadruple check datasheets. At first, they look complicated, but they are not that hard to read once you get used to them.
2. Work with your team and the teaching team every step of the way and get feedback on everything, components used, schematic connects, etc.
3. Favor simplicity over complexity. This is your first surface-mount PCB, and even things that seem simple can be more than you expect.
4. Invest in your own soldering station with surface mount and through-hole capability, and please get good paste and flux, it'll make your connections so much better
5. Devote a large amount of time to this class, but try to make it fun, it's one of the most interesting projects I've had, and you learn so much from it
6. NEVER GIVE UP!!!!

