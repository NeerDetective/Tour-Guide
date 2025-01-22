<h1>Software Tour Guide</h1>

<h2>Description</h2>
Project consists of creating a simple software tour guide robot using python and third party software to create a guide that you could interact with and give directions to navigate the campus of Caribbean Maritime University. It also answers questions about the school.
<br />


<h2>Languages, Utilities and Libraries Used Used</h2>

- <b>Python</b> 
- <b>Speech Recognition</b>
- <b>Pyttsx3</b> 
- <b>OpenCV</b>
- <b>Google SpeechRecognition API</b> 

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
First Part Code: <br/>

import speech_recognition as sr
import pyttsx3


# Initialize the text-to-speech engine
text_to_speech_engine = pyttsx3.init()

# Function to take simple oral question and provide speech response
    def take_and_respond_to_question():
  # Initialize the speech recognition engine
    speech_recognizer = sr.Recognizer()

    try:
  # Listen for the question from the user
        with sr.Microphone() as source:
            print("Please ask your question:")
            audio = speech_recognizer.listen(source)

  # Convert the speech to text
        question = speech_recognizer.recognize_google(audio)
        print("You asked:", question)
  # Process the question and generate a response
        response = generate_response(question)
  # Respond to the user's question using text-to-speech
        print("Response:", response)
        text_to_speech_engine.say(response)
        text_to_speech_engine.runAndWait()

    except sr.UnknownValueError:
        print("Sorry, I could not understand the question.")
    except sr.RequestError as e:
        print(f"Could not request results from Google Speech Recognition service; {e}")

  # Function to generate a response based on the question
    def generate_response(question):
  # Add your response generation logic here based on the question
  # For simplicity, let's just provide a static response for demonstration purposes.
    return "I am a basic tour guide robot. How can I assist you today?"

# Function to capture and recognize faces
    def recognize_faces():
  # Load a sample image and learn how to recognize it
    sample_image = face_recognition.load_image_file("sample_image.jpg")
    sample_face_encoding = face_recognition.face_encodings(sample_image)[0]

  # Load an image with unknown faces and recognize them
    unknown_image = face_recognition.load_image_file("unknown_image.jpg")
    unknown_face_encodings = face_recognition.face_encodings(unknown_image)
  # Compare the unknown faces with the known sample face
    for unknown_face_encoding in unknown_face_encodings:
   # Check if the unknown face matches the sample face
        results = face_recognition.compare_faces([sample_face_encoding], unknown_face_encoding)
        if results[0]:
            print("This face is a match!")
        else:
            print("This face is not recognized.")

# Main function to control the tour guide robot
    if _name_ == "_main_":
    take_and_respond_to_question()
    recognize_faces()

    recognize_faces()

<br />
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
