# ai-project
A web application built with Python (Django/Flask) featuring REST APIs and clean architecture.
import random

responses = {
    "hello": ["Hi!", "Hello there!", "Hey! 👋"],
    "how are you": ["I'm fin

        if user == "exit":
            print("🤖 AI Chatbot: Goodbye!")
            break

        found = False
        for key in responses:
            if key in user:
                print("🤖 AI Chatbot:", random.choice(responses[key]))
                found = True
                break

        if not found:
            print("🤖 AI Chatbot: Sorry, I didn't understand that 😅")

chatbot()
