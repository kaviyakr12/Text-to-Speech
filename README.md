Text-to-Speech Script
This script utilizes the pyttsx3 library to convert text from a file into speech. The script reads each line from a specified text file and then vocalizes it using the text-to-speech engine.

Prerequisites
Ensure you have Python installed on your system. This script uses the pyttsx3 library, which can be installed using pip.


pip install pyttsx3
File Structure
text_to_speech.py: The main script to run the text-to-speech functionality.
demo.txt: The text file that contains the content to be read aloud. Ensure this file is placed in the correct directory as specified in the script.
Usage
Update the File Path: Modify the file_path variable in the script to point to your text file. For example:

file_path = r"C:\path\to\your\file\demo.txt"
Run the Script: Execute the script using Python. Open a terminal or command prompt and run:

python text_to_speech.py
Listen to the Text: The script will read each line from the specified file and use the pyttsx3 engine to vocalize it. There will be a 1-second pause between each line.

Script Explanation
Importing Libraries

import pyttsx3
from time import sleep
pyttsx3: A text-to-speech conversion library in Python.
sleep: Used to add a delay between the reading of each line.
Reading the Text File

file_path = r"C:\Users\PAVITHRA\OneDrive\Documents\Desktop\kaviya\demo.txt"
with open(file_path, "r") as b:
    book = b.readlines()
Opens the text file in read mode and reads all lines into a list book.
Initializing the Text-to-Speech Engine

engine = pyttsx3.init()
Initializes the pyttsx3 text-to-speech engine.
Reading Each Line Aloud

for line in book:
    engine.say(line)
    engine.runAndWait()
    sleep(1)
Iterates over each line in the text file.
Uses engine.say(line) to queue the line for speech.
Calls engine.runAndWait() to process the speech queue.
Adds a 1-second pause between each line with sleep(1).
Customization
Change the Voice: Modify the voice by configuring the pyttsx3 engine properties.
Adjust the Rate: Change the rate of speech by adjusting the rate property of the engine.
Pause Duration: Modify the sleep duration to change the pause between lines.

# Example of changing voice and rate
voices = engine.getProperty('voices')
engine.setProperty('voice', voices[1].id)  # Change index for different voices
engine.setProperty('rate', 150)  # Adjust rate (default is 200)
Troubleshooting
Ensure the file path is correct and the file exists.
Make sure pyttsx3 is installed and accessible in your Python environment.
Check the pyttsx3 documentation for more configuration options and troubleshooting tips.
