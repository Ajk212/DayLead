# DayLead
This repository holds the files and information regarding the DayLead's development and details steps needed for replication


## Design Overview


### Description
With most modern devices and apps, accounts need to be made and internet connections are required. Tools to help productivity suffer due to these demands since they can lead users away from their goals.  The DayLead is a personal assistant device designed to combat unneeded services and boost productivity. There are no WiFi or Bluetooth connections, meaning the device is completely offline, allowing work without distraction or interruptions. The design comprises a 10.1" touchscreen monitor paired with a Raspberry Pi 4b. These devices connect seamlessly in a wall-mounted enclosure which can be placed anywhere due to the convenient size. The device gives users access to an alarm, stopwatch, calendar, kanban board, habit tracker, and reminder page. After the user enters their local date and time, the DayLead dynamically updates to keep accurate readings.

IMAGE OF FULL ENCLOSURE 

### Original Design
Starting this project, I initially planned to create the code required through the Raspberry Pi and Linux. After researching app development and cross-platform integration, I instead opted to move forward coding in Python with Kivy as the app framework. The function of each page kept the same overall ideas, but what was included within each page had changed through development. Before starting this project, I had minimal exposure to Python and needed to learn the language first, so many ideas needed to be cut to meet the final deadline. Each cut function will be added in a future 2.0 update. Some cut functions include: multiple alarms, dynamic calendar, information storage, morning routines, habit streak counter, daily mood tracker, and more.

### Justification
This project has been one of the best learning experiences for me. Previous projects have prepared me to write simple programs and design hardware, but as an aspiring software engineer, I need more exposure to learning new languages and creating more complex and demanding programs. The hardware portion of this design is fairly simplistic, so I could devote most of my time to learning app development techniques, Python syntax, Kivy framework, and experiencing each part of an app's composition, like UI design. The creation and editing of images, icons, and sound files was an aspect of this project I did not account for, but quickly adapted to keep pace with my timeline. While I first dreaded cutting any features, I realized that cutting content is a part of the development cycle. While I could sit on a single page and get everything done, other functions would suffer in return. Experiencing the balance of developing such an app has strengthed my resolve and has equipped me to learn more, and tackle bigger challenges in the future.

## Preliminary Design Verification
The preliminary testing of this project was fairly straightforward. The use of Kivy framework ensures compatibility between most devices and alleviates some issues, like scaling and widget size. Kivy automatically detects and formats the program window depending on the device used. Additionally, each function of the app was designated its own page, meaning the code could be created without fear of conflict. Not many values are sent between screens, so testing went smoothly, allowing me to move on if I were to get stuck on a page for too long. Early testing with the Raspberry Pi revealed issues revolving around Python library dependencies, but Kivy and Python documentation pages guide the process of installing on devices like this and common troubleshooting methods. 

## Design Implementation
The final design of the application houses 7 main screens. Each screen has its own class and is accessed by the top navigation bar on the Home screen. The description of each page is as follows.

### Home Screen
The home screen houses buttons to navigate to each page, as seen at the top. The clock button at the bottom left corner prompts a dialog box to choose your local time and date. After receiving this information, the system updates to the given values. There are additionally two spaces on either side of the time to display the user's habits and reminders. These only appear after the user has entered them on their respective pages.

![Default_Home](https://github.com/user-attachments/assets/2183d184-8f3b-4ed2-96c5-6b19f026f1bf)
Home Screen on launch

![Time_set](https://github.com/user-attachments/assets/8cb4e27a-564b-49af-ae92-790c67534459)
Time Dialog

![Date_set](https://github.com/user-attachments/assets/74ffd649-6924-4dd3-859e-8eead413960f)
Date Dialog

![Updated_Home](https://github.com/user-attachments/assets/bbf94e8e-70d9-4f0b-a6c0-e83da77020a2)
Home Screen with added values
