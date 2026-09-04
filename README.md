# Screenshot-Capture
A simple Python script that automatically captures screenshots of your screen at regular intervals and saves them as JPG images.
Features
Capture screenshots automatically in an infinite loop.
Configure the screenshot storage directory.
Capture screenshots by:
Hours
Minutes
Seconds
Configure how many screenshots should be taken per hour, minute, or second.
Screenshots are saved using the current time as the filename.
Stop the script safely using Ctrl+C.
Requirements
Python 3.x
pyautogui

Install the required dependency:

pip install pyautogui
Usage

Run the script with:

python "Capture Screenshots At Regular Intervals of Time - Copy(2).py"

By default:

Screenshots are stored in ./images
The interval type is hour
Frequency is 1

The script creates the output directory if it does not already exist.



Specifies the directory where screenshots should be saved.

python script.py --path ./screenshots



Specifies the time unit used for the screenshot frequency.

Supported values:

Value	Meaning
h	Hours
m	Minutes
s	Seconds


Specifies how frequently screenshots should be captured within the selected time unit.

This results in one screenshot approximately every 30 minutes.

The frequency is converted into seconds internally.

Examples
Screenshot every hour
python script.py -t h -f 1
Two screenshots per hour
python script.py -t h -f 2
One screenshot every 10 minutes
python script.py -t m -f 1
Six screenshots per minute
python script.py -t m -f 6
Save screenshots to a custom directory
python script.py -p ./screenshots -t m -f 5
Output



Screenshots are saved as JPG files using the current time:

images/
├── 23_10_01.jpg
├── 23_11_01.jpg
├── 23_12_01.jpg
└── ...

The filename is generated from the current local time in HH_MM_SS format.

After each screenshot, the script prints:

23_10_01.jpg saved successfully.
Stopping the Script

The script continuously captures screenshots until it is interrupted.

Press:

Ctrl+C

The script catches the keyboard interrupt and prints:

End of script by user interrupt




How It Works
Parse command-line arguments.
Calculate the delay between screenshots.
Create the output directory if necessary.
Take a screenshot using pyautogui.
Save the screenshot as a JPG.
Wait for the configured interval.
Repeat until the user stops the program.
Notes
The current implementation enforces a minimum delay of 1 second between screenshots.
The --type s option is listed in the argument help, but the current implementation does not contain a branch that calculates seconds directly.
Screenshots continue indefinitely until manually interrupted.
