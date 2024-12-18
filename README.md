# DayLead
This repository holds the files and information regarding the DayLead's development and details the steps needed for replication
All software files are contained in DayLead.zip, including the main code, kv design file, Icons file, and audio files
The enclosure design is held within Enclosure.svg

10.1 Inch Touchscreen used - https://www.amazon.com/Hosyond-Capacitive-Touchscreen-1280x800-Raspberry/dp/B0CLQZ48BF/ref=sr_1_4?sr=8-4
Raspberry Pi 4b - https://www.digikey.com/en/products/detail/raspberry-pi/SC0193-9/10258782

## Design Overview


### Description
With most modern devices and apps, accounts need to be made and internet connections are required. Tools to help productivity suffer due to these demands since they can lead users away from their goals.  The DayLead is a personal assistant device designed to combat unneeded services and boost productivity. There are no WiFi or Bluetooth connections, meaning the device is completely offline, allowing work without distraction or interruptions. The design comprises a 10.1" touchscreen monitor paired with a Raspberry Pi 4b. These devices connect seamlessly in a wall-mounted enclosure which can be placed anywhere due to the convenient size. The device gives users access to an alarm, stopwatch, calendar, kanban board, habit tracker, and reminder page. After the user enters their local date and time, the DayLead dynamically updates to keep accurate readings.

![Enclosure_full](https://github.com/user-attachments/assets/3d961d7e-603b-4bfb-bf9e-61b5cce210d6)

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

### Alarm 
The alarm screen has 4 main functions, setting an alarm, resetting the alarm, changing alarm type, and controlling a stopwatch. The user interface is quite straightforward, where setting the alarm is similar to setting the local time. Changing the alarm type can be done with the "Light Sleeper" button. When the text shows as "Light Sleeper", a gentle, but effective alarm is played upon the activation time. When pressed, the text changes to "Heavy Sleeper" and alters the alarm sound to a louder beeping. 

![Alarm_Screen](https://github.com/user-attachments/assets/86794fc7-b00f-49fc-8466-76c1dcc9eae0)
Alarm Screen layout

![Alarm_trigger](https://github.com/user-attachments/assets/553b3e5c-085b-48d6-b2bc-17f9b5dc7b21)
Alarm trigger

### Calendar 
The calendar screen is meant to dynamically update with the user's local time, highlighting the current date and can give a look into past or future months. This page is currently incomplete but has a general layout instantiated. 

![Calendar_screen](https://github.com/user-attachments/assets/b0b2b17c-9510-4ba4-be17-486b45990f70)
Calendar Screen Layout

### Kanban 
The kanban screen provides an effective tool to boost productivity. Acting as a To-Do list, the user can add notes to the "Backlog" column. When the respective note is tapped, it moves to the next column, "Underway", and finally to "Complete". When a note is tapped in the "Complete" section, it is removed from the page and deleted. The notes move to the first available position in the next column, allowing for up to 15 notes to be active at one time. 

![Kanban_Screen](https://github.com/user-attachments/assets/3b70ebca-1402-46e9-828c-cbef05c5268b)
Kanban Screen layout

### Habits
The habits screen can allow a user to catalog and keep track of routines they would like to make or break. The user can add up to 5 habits, with each having a delete button, completion indicator, and streak tracker. The completion indicator, when tapped, changes to either Complete/Incomplete to mark whether the habit was kept today. The streak function is meant to update at the end of the day, adding a point to every habit completed. This function is currently unavailable due to its reliance on the calendar page. All habits added are also logged on the home screen.

![Habit_Screen](https://github.com/user-attachments/assets/279fa15f-8bc5-4bc2-a0b4-2d7ab6aedb6b)
Habit Screen layout

### Reminders
The reminders screen allows 6 reminders to be added. Each reminder can be kept or deleted with the red button. All reminders are displayed on the main page. This page is similar to the habits page but is meant to be used for short-term items, like doctor's appointments or homework due dates.

![Reminder_page](https://github.com/user-attachments/assets/2197f7a7-8162-401a-b558-519a1d2235be)
Reminder Screen layout

### Design Practices and Challenges
I wanted to ensure the best user experience for this application. One major component of a good user experience is ease of use. The straightforward design of each page, along with the navigation to each page, ensure no user will be lost in layers of menus, trying to find what they want. All functions are clearly labeled and contribute towards productivity boosts. 

Throughout the creation of this project, many challenges were faced. The largest challenge was my lack of familiarity with Python and Kivy. By following the extensive online documentation and watching explanation videos I was able to keep a steady pace of work while learning Python syntax and kivy methods. Other than the learning curve, time was a major constraint to work around. The time constraint is the reason some functionality is missing or cut, but is also why I was able to achieve so much in such a short time. The final main challenge faced was interconnecting functions and preventing code bloat. The calendar screen, for example, had functional code to implement but slowed the program greatly. I removed this code so that the rest of the program may run as intended, and will work to reduce the load that it puts on the system.

## Design Testing
My plan for testing my app was to ensure the completion of one section as much as possible before moving on. The main benefit of this plan was that most of the pages did not rely on the completion of any other, so they could be constructed independently. Once a page reached an acceptable state, I tried to break it. If it were to break, I would patch the code and move to the next function. I began by creating the home page and the navigation buttons. After that, I worked on the page I had ideas for at the moment. While this was a separate plan, it worked out fairly well, with the only non-functional page being the calendar. While I do have a way to create the months accurate to the day, it slowed the program greatly. I opted for its removal so all else could run better and looked to find a more optimized solution.

![App_Showcase](https://github.com/user-attachments/assets/c70b0e2a-0363-4ead-b9c9-332b4ac47a3e)
Early app iteration

![2ndItteration](https://github.com/user-attachments/assets/02db1537-f471-4fab-a422-99ac2a14ffda)
Second app iteration

## Summary and Future Work
This project has greatly enhanced my understanding of Python and has given me insight into how apps are developed and integrated with embedded systems. I am satisfied with the progress I've made with this 1.0 version and have many plans for a 2.0 update. Functions I plan to work further on include: optimizing the calendar page, multiple set alarms, more accurate timekeeping, structure improvement, KV file optimization, saving data between sessions, and many more. Now that there is no time constraint, the 2.0 version will have much more functionality and will hopefully run smoother. This has been one of the most entertaining and educational projects I've done to date, and I plan to continue with it. 

# Refrecnes
Special thanks to the CodeMy.com YouTube channel. Their Kivy tutorial playlist helped me understand the formatting and syntax greatly.

"Light Sleeper" alarm file - https://pixabay.com/users/einnt-20261572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=249206

"Heavy Sleeper" alarm file - https://pixabay.com/users/freesound_community-46691455/?utm_source=link-attribution&utm_medium=referral&utm_campaign=music&utm_content=29480

Clock Icon - created by CreativeCons on FlatIcon.com

Lightbulb Icon - created by Mihimihi on FlatIcon.com

Post-It Tabs - Designed by Freepik on Freepik.com
