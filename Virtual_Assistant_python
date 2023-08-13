import speech_recognition as sp # take microphone input from user and returns string output
import pywhatkit # youtube search
import os
import datetime # for current time
import wikipedia 
import webbrowser # for web browser
import time
import pyttsx3 # text to speech converter 

runn= pyttsx3.init('sapi5') #here sapi5 is use to take inbuilt window voice for male=0 and female=1
voice_male_or_female = runn.getProperty('voices') #available voice in computer
runn.setProperty('voice', voice_male_or_female[0].id) #set voice

def speak(audio):
    runn.say(audio)
    runn.runAndWait() #audible to us

def wish():
    hour = int(datetime.datetime.now().hour)
    if hour>=0 and hour<12:
        speak("Good Morning!")

    elif hour>=12 and hour<18:
        speak("Good Afternoon!")   

    else:
        speak("Good Evening!")  

    speak("I am Alexa. Please tell me how may I help you?")       

def Command():
    r = sp.Recognizer()
    with sp.Microphone() as source:
        print("Listening...")
        r.pause_threshold = 1 # runandwait
        r.adjust_for_ambient_noise(source) #for filtering
        audio = r.listen(source)
       
    try:
        print("Recognizing...")    
        query = r.recognize_google(audio, language='en-in')

    except Exception as e: 
        print("Say that again please...")  
        return "None"
    return query

if __name__ == "__main__":
    wish()
    while 1:
        query = Command().lower()

        if 'wikipedia' in query:
            print(query)
            speak('Searching Wikipedia...')
            query = query.replace("wikipedia", "")
            results = wikipedia.summary(query, sentences=2) 
            speak("According to Wikipedia")
            print(results)
            speak(results)

        elif 'open youtube' in query:
            print(query)
            webbrowser.open("youtube.com")

        elif 'open google' in query:
            print(query)
            webbrowser.open("google.com")

        elif 'open stackoverflow' in query:
            print(query)
            webbrowser.open("stackoverflow.com")   

        elif 'play music' in query:
            print(query)
            music_dir = 'D:\\songs'
            songs = os.listdir(music_dir)
            print(songs)    
            os.startfile(os.path.join(music_dir, songs[0]))

        elif 'the time' in query:
            print(query)
            strTime = datetime.datetime.now().strftime("%H:%M:%S")  
            speak(f"Sir, the time is {strTime}")
            print(strTime)

        elif 'exit' in query:
            print(query)
            speak("thank you for giving me your time")
            print("thank you for giving me your time")
            break
    
        elif 'open vs code' in query:
            print(query)
            codePath = "C:\\Users\\Vishwa\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe"
            os.startfile(codePath) 

        elif 'how are you' in query:
            print(query)
            print("I am fine, Thank you")
            speak("I am fine, Thank you")

        # elif 'fine' or 'good' in query:
        #     speak("Good to know that you are fine")

        elif 'who made you' in query:
            print(query)
            speak("I have been created")

        elif 'search' in query or 'play' in query:
            print(query)
            query = query.replace("search", "")
            query = query.replace("play", "")		
            webbrowser.open(query)

        elif 'who are you' in query:
            print(query)
            speak("I am your virtual assistant.")

        elif "don't listen" in query or "stop listening" in query:
            print(query)
            speak("for how much time you want to stop your assistant from listening commands")
            a = int(Command())
            time.sleep(a)
            print(a)

        elif "write a note" in query:
            print(query)
            speak("What should i write?")
            note = Command()
            print(note)
            file = open('text.txt', 'a')
            file.write(note)
            speak("I have appended your notes")
            print("I have appended your notes")
            
            
        elif "show note" in query:
            print(query)
            speak("Showing Notes")
            file = open("text.txt", "r")
            print(file.read())
            speak(file.read())
            
        elif 'shutdown system' in query:
            print(query)
            speak("Hold On a Sec ! Your system is on its way to shut down")
            os.system("shutdown /s /t 30")
            
        elif 'play' in query:
            print(query)
            speak("opening youtube")
            pywhatkit.playonyt(query)
