# VITBOT - an AI-Chatbot-with-Tensorflow
This is a Chatbot which i created for my AI-NLP project. It is fully written in python and for training and modelling i have used Tensorflow. Chatbot can be integrated with web too, Using flask nd tensorflow serving, but i haven't done that yet. 

# Working  
So, the flow of the chatbot is as follows:
  1. First we have a file called 'intents.json', in this file we have a set of predefined questions and answers. All questions and answers can be seperated by 'tags'. 'tags' here means a specific topic or category of a question. For ex, tag=Canteen means the question asked by the user falls into canteen category.  
  2. You can easily add or delete questions/answers into/from the intents.json file.  
  3. We have a neural network which will train on the questions, obviously we need to convert text into bag-of-words representation in order to do that. Here, we will learn the association between the question and the tag. Which means our feature variable is Bag of words representation of the questions and our target varaible is the tag associated with those questions. Yes, it's a classification task.
  4. Once we find the tag, we just need to return an answer for that tag entry through the json file.
  
## Example:
```
   {
                        "tag": "goodbye",
                        "patterns": [
                                "cya",
                                "see you",
                                "bye bye",
                                "See you later",
                                "Goodbye",
                                "I am Leaving",
                                "Bye",
                                "Have a Good day",
                                "talk to you later",
                                "tyyl",
                                "i got to go",
                                "gtg"
                        ],
                        "responses": [
                                "Sad to see you go :(",
                                "Talk to you later",
                                "Goodbye!",
                                "Come back soon"
                        ],
                        "context_set": ""
                },
  ```
So as you can see here, for tag='goodbye' people can say it in multiple ways, so for a single tag goodbye their are multiple questions, and also if our chatbot only answers one single answer then it would be so boring, that's why we have multiple answers to the goodbye tag, and each time it will choose randomly from that set.  
User Enters --> See you / see you later/ bye --> bot predicts tag='goodbye' --> inside intents.json looks for tag='goodbye' return random response from responses list. So that's the flow.


