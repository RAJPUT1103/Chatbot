# Chatbot
import random

# Predefined responses
responses = {
    "hi": ["Hello!", "Hi there!", "Hey!"],
    "how are you": ["I'm doing well, thank you!", "I'm good, thanks for asking.", "All good on this side!"],
    "bye": ["Goodbye!", "See you later!", "Bye! Take care!"],
    "default": ["Sorry, I didn't understand that.", "Could you please repeat that?", "I'm not sure what you mean."]
}

def chatbot(user_input):
    # Convert user input to lowercase
    user_input = user_input.lower()
    # Check if user input matches predefined responses
    for key in responses:
        if key in user_input:
            return random.choice(responses[key])
    # If no match found, return a default response
    return random.choice(responses["default"])

def main():
    print("Welcome to the Chatbot!")
    print("You can start chatting. Type 'bye' to exit.")
    while True:
        user_input = input("You: ")
        if user_input.lower() == 'bye':
            print(chatbot(user_input))
            break
        else:
            print("Bot:", chatbot(user_input))

if __name__ == "__main__":
    main()
