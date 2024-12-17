# DayLead
This repository holds the files and information regarding the DayLead's development and replication instructions


# Design Overview


## Description
With most modern devices and apps, accounts need to be made and internet connections are required. Tools to help productivity suffer due to these demands since they can lead users away from their goals.  The DayLead is a personal assistant device designed to combat unneeded services and boost productivity. There are no WiFi or Bluetooth connections, meaning the device is completely offline, allowing work to be done without distraction or interruptions. The design comprises a 10.1" touchscreen monitor paired with a Raspberry Pi 4b. These devices connect seamlessly in a wall-mounted enclosure which can be placed anywhere due to the convenient size. The device gives users access to an alarm, stopwatch, calendar, kanban board, habit tracker, and reminder page. After the user enters their local date and time, the DayLead dynamically updates to keep accurate readings.

IMAGE OF FULL ENCLOSURE 

## Original Design
Starting this project, I initially planned to create the code required through the Raspberry Pi and Linux. After researching app development and cross-platform integration, I instead opted to move forward coding in Python with Kivy as the app framework. The function of each page kept the same overall ideas, but what was included within each page had changed through development. Before starting this project, I had minimal exposure to Python and needed to learn the language first, so many ideas needed to be cut to meet the final deadline. Each cut function will be added in a future 2.0 update. Some cut functions include: multiple alarms, dynamic calendar, information storage, morning routines, habit streak counter, daily mood tracker
