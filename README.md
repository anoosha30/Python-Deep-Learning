# Python-Deep-Learning
Project - Speech Recognition - Python &amp; Deep Learning

import speech_recognition as sr

# Initialize the recognizer
r = sr.Recognizer()

# Function to recognize speech
def recognize_speech(filename):
    # Load the audio file
    with sr.AudioFile(filename) as source:
        # Read the entire audio file
        audio = r.record(source)
        
        try:
            # Use deep learning model to recognize speech
            recognized_text = r.recognize_google(audio)
            print("Recognized text: " + recognized_text)
        except sr.UnknownValueError:
            print("Speech recognition could not understand audio")
        except sr.RequestError as e:
            print("Could not request results from Google Speech Recognition service; {0}".format(e))

# Path to the audio file
audio_file = "path/to/audio/file.wav"

# Call the speech recognition function
recognize_speech(audio_file)
