AUTOMATIC-SUBJECT-TIME-ALLOCATOR

A simple Java console-based Timetable Scheduler that automatically generates a weekly timetable based on the subjects provided by the user. The program distributes subjects evenly across periods and days, making it useful for students or schools who need a quick timetable layout.

Features

1. Add multiple subjects through user input
2. Set the number of periods per day
3. Automatically generate a weekly timetable (Monday–Saturday)
4. Subjects are assigned cyclically to avoid imbalance
5. Neatly displays the timetable in a table format
6. Fully console-based and easy to use

Tech Stack

1. Language: Java
2. Type: Comand prompt Application
3. Storage: In-memory (no file saving in this version)

Project Structure

1. Entry point (contains the main method)
2. Handles user input through Scanner
3. Stores the list of subjects
4. Sets number of periods per day
5. Automatically generates the weekly timetable (Monday–Saturday)
6. Prints the timetable in a table format

How to Run

1.	Make sure Java (JDK 8+) is installed.
2.	Save the code in a file named TimetableScheduler.java.
3.	Open a terminal in the file directory.
4.	Compile the code:  javac TimetableScheduler.java
5.	Run the program:   java TimetableSchedule
   
Program Flow

When you run the program, the terminal will ask: 1. Enter number of subjects
                                                 2.	Enter each subject name
                                                 3.	Enter number of periods per day

Data Handling

1. The timetable is generated and stored in memory only (no file persistence).
2. The timetable follows a cyclic subject assignment to keep distribution balanced across days and periods.

Future Improvements

1. Allow saving and loading timetable from a text file
2. Add editing or removing subjects
3. Add support for teacher names, room numbers, or time durations
4. Add option to customize days (Mon–Fri or Mon–Sat)

