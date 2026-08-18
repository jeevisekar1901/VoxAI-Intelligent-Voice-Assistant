🤖 AI Voice Assistant Using Python

📌 Project Overview

The **AI Voice Assistant Using Python** is an interactive voice-controlled assistant developed using Python. The project enables users to communicate with the computer through **natural voice commands** instead of traditional keyboard and mouse interactions.

The assistant captures the user's voice through a microphone, converts the speech into text using **Speech Recognition**, analyzes the recognized command, performs the requested operation, and responds to the user using **Text-to-Speech (TTS)**.

This project demonstrates the practical implementation of **Artificial Intelligence, Speech Recognition, Natural Language Interaction, Python Automation, and Text-to-Speech technologies** in a simple and beginner-friendly application.

The project is designed as an educational and portfolio project for students interested in **Python, Artificial Intelligence, Machine Learning, Automation, and Voice-Based Applications**.


✨ Features

🎙️ 1. Speech Recognition

The assistant listens to the user's voice through the microphone and converts the spoken words into text.

 🔊 2. Text-to-Speech

The assistant converts its responses from text into human-readable speech, allowing users to interact with the system without looking at the screen.

📚 3. Wikipedia Search

The assistant can search Wikipedia for information about a person, place, technology, or other general topics and provide a short summary.

⏰ 4. Time Information

The assistant can recognize time-related commands and announce the current time.

🤖 5. Voice-Based Interaction

Users can interact with the assistant using predefined voice commands.

⚡ 6. Automated Responses

The assistant analyzes recognized commands and generates appropriate responses automatically.

🐍 7. Python-Based Implementation

The complete project is developed using Python and uses various Python libraries for speech recognition, text-to-speech, information retrieval, and automation.


🛠️ Technologies Used

* **Python**
* **SpeechRecognition**
* **PyAudio**
* **pyttsx3**
* **Wikipedia**
* **datetime**
* **Python Standard Library**


🏗️ System Workflow

💻 Installation and Setup

Follow the steps below to run the project on your computer.

 1️⃣ Install Python

First, install Python on your system.

Download Python from the official Python website:

[https://www.python.org/downloads/](https://www.python.org/downloads/)

During installation on Windows, make sure to enable:

☑ Add Python to PATH

After installation, verify Python:

python --version

or:

py --version

You should see the installed Python version.



 2️⃣ Clone the Repository

Open Command Prompt, PowerShell, or the VS Code terminal and run:

git clone https://github.com/YOUR-USERNAME/AI-Voice-Assistant-Python.git

Move into the project directory:

cd AI-Voice-Assistant-Python


 3️⃣ Create a Virtual Environment

Creating a virtual environment is recommended because it keeps the project's dependencies separate from other Python projects.

Open Command Prompt, PowerShell, or the VS Code terminal and run:

git clone https://github.com/YOUR-USERNAME/AI-Voice-Assistant-Python.git

Move into the project directory:

cd AI-Voice-Assistant-Python

**Windows**

Activate the virtual environment using:

venv\Scripts\activate

**macOS/Linux**

Use:

source venv/bin/activate
After activation, you should see something similar to:

(venv)
in your terminal.


 📦 4️⃣ Install Required Libraries

Upgrade pip:

python -m pip install --upgrade pip

Then install the project dependencies:

pip install -r requirements.txt

If you are installing the packages manually, use:

pip install SpeechRecognition
pip install pyttsx3
pip install wikipedia

For microphone input, the project also requires PyAudio.

pip install PyAudio



🎤 5️⃣ Check Microphone Access

The assistant requires a working microphone.

On Windows:

Settings → Privacy & Security → Microphone

Make sure microphone access is enabled for applications.

Also check:

Settings → System → Sound → Input

and make sure the correct microphone is selected.



 ▶️ 6️⃣ Run the Application

After installing all dependencies, run:

python ai_assistant.py

The assistant will start listening for voice commands.

Speak clearly into the microphone and wait for the assistant to process your command

## Code##
# pip install SpeechRecognition
# pip install pyttsx3
# pip install pywhatkit
# pip install wikipedia

import speech_recognition as sr
import pyttsx3
import pywhatkit
import wikipedia
import datetime

r = sr.Recognizer()
phone_numbers = {"ravi": "1234567890", "john": "0987654321", "alice": "5555555555"}
bank_account_numbers = {"tt": "1111222233334444", "mm": "5555666677778888"}

def speak(command):
    engine = pyttsx3.init()
    voices = engine.getProperty('voices')
    engine.setProperty('voice', voices[1].id)  
    engine.say(command)
    engine.runAndWait()

def commands():
    try:
        with sr.Microphone() as source:
            r.adjust_for_ambient_noise(source)
            print('Listening... Ask now...')
            audioin = r.listen(source)
            my_text = r.recognize_google(audioin)
            my_text = my_text.lower()
            print(my_text)

            # ask to play a song
            if 'play' in my_text:
                my_text = my_text.replace('play','')
                speak('playing' + my_text)
                pywhatkit.playonyt(my_text)

            # ask date
            if 'date' in my_text:
                today = datetime.date.today()
                speak(today)

            # ask time
            if 'time' in my_text:
                timenow = datetime.datetime.now().strftime('%H:%M')
                speak(timenow)

            # ask details about any person
            if 'who is' in my_text:
                my_text = my_text.replace('who is','')
                info = wikipedia.summary(person,1)
                speak(info)

            # ask phone numbers
            if "phone number" in my_text:
                names = list (phone_numbers)
                print(names)
                for name in names:
                    if name in my_text:
                      print(name + " phone number is " + phone_numbers[name])
                      speak(name + " phone number is " + phone_numbers[name])

            #ask personal bank account numbers
            if "bank account number" in my_text:
                banks = list (bank_account_numbers)
                for bank in banks:
                    if bank in my_text:
                      print(bank + " bank account number is " + bank_account_numbers[bank])
                      speak(bank + " bank account number is " + bank_account_numbers[bank])



            # if not recognized
            else:
                speak("Please ask correct question")



    except:
        print('Error in capturing microphone...')

commands()


# 🚀 Future Enhancements

The current project can be extended with more advanced Artificial Intelligence capabilities.

Possible future improvements include:

## 🤖 AI-Powered Conversations

Integrate a modern AI/LLM API to enable more natural conversations.

## 🌐 Web Search

Add web search capabilities so that the assistant can retrieve current information.

## 📧 Email Automation

Allow users to compose and send emails through voice commands.

## 🎵 Music Control

Add commands for playing music or controlling media applications.

## 🌦️ Weather Information

Integrate a weather API to provide real-time weather information.

## 📅 Task and Reminder Management

Allow users to create reminders and manage daily tasks using voice commands.

## 🏠 Smart Home Integration

Connect the assistant with IoT devices for voice-controlled home automation.

## 🌍 Multilingual Support

Add support for multiple languages and regional speech recognition.

## 🧠 Natural Language Processing

Use NLP techniques to understand more complex user commands instead of relying only on predefined keywords.

## 🔒 Voice Authentication

Implement speaker recognition so that the assistant can identify authorized users.







