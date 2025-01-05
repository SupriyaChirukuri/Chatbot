# Chatbot
Chatbot Using NLP

This project implements a simple chatbot using Natural Language Processing (NLP) techniques with Python. The chatbot is designed to assist users with predefined responses based on user input, making it suitable for applications like hotel management or customer support.

Features

Interactive User Interface:

Developed using Streamlit to provide an intuitive and web-based chat interface.

NLP Chat Logic:

Uses nltk's Chat module to handle input and output based on predefined response pairs.

Customizable Responses:

Responses can be easily updated or expanded by modifying the response pairs.

Quick Deployment:

Deployable locally or on platforms like Google Colab using ngrok for public access.

Prerequisites

Before running the chatbot, ensure you have the following installed:

Python 3.7+

Required libraries:

streamlit

nltk

pyngrok (for Google Colab deployments)

Install the required libraries using:

pip install streamlit nltk pyngrok

Setup Instructions

Local Deployment

Clone the Repository:

git clone <repository_url>
cd <repository_directory>

Run the Streamlit App:

streamlit run app.py

Access the Chatbot:

The app will open in your default browser, or you can visit http://localhost:8501.

Google Colab Deployment

Upload the Project Code to Colab.

Install Dependencies:

!pip install streamlit nltk pyngrok

Run the Streamlit App in Colab:

!streamlit run app.py &>/dev/null &

Expose App Publicly Using ngrok:

from pyngrok import ngrok
public_url = ngrok.connect(port=8501)
print(f"Access the chatbot at: {public_url}")

Open the Public URL to interact with the chatbot.

Code Overview

Main File: app.py

Chatbot Logic:

from nltk.chat.util import Chat, reflections

pairs = [
    [r"(hi|hello|hey)", ["Hello! How can I assist you?"]],
    [r"(bye)", ["Goodbye! Have a great day!"]],
]

chatbot = Chat(pairs, reflections)

Streamlit Integration:

import streamlit as st

st.title("Chatbot")
user_input = st.text_input("You:")

if user_input:
    response = chatbot.respond(user_input)
    st.write(f"Chatbot: {response}")

Suggestions for User Input (Optional):

suggestions = ["Good evening", "Book a room", "Cancel a booking"]
for suggestion in suggestions:
    st.button(suggestion)

Customization

Adding New Responses:

Modify the pairs list in app.py.

Example:

[r"(how are you)", ["I'm just a bot, but I'm doing great! How about you?"]]

UI Customization:

Update the Streamlit layout and styling.

Example Interactions

User: HiChatbot: Hello! How can I assist you?

User: Book a roomChatbot: Sure! Please provide your check-in and check-out dates.

User: ByeChatbot: Goodbye! Have a great day!


