**What is a chatbot and why is it needed?**

A chatbot is a computer program or an AI system created to converse with humans, typically online. It serves various purposes, such as providing information, answering queries, and assisting users with tasks. Chatbots come in two main types: retrieval-based and generative-based models.

Chatbots leverage natural language processing (NLP) and machine learning methods to comprehend and address user inquiries. They range from straightforward, rule-based systems that adhere to predefined guidelines for particular keywords or phrases, to more sophisticated models that utilize machine learning algorithms to learn from interactions, enhancing their responses progressively.

**1. Retrieval based Chatbots**

Retrieval-based chatbots rely on predefined input patterns and responses. They select the appropriate response using heuristic methods, making them suitable for goal-oriented interactions. These chatbots are customizable to provide tailored experiences for users.

**2. Generative based Chatbots**

Generative models, on the other hand, do not use predefined responses. Instead, they employ sequence-to-sequence neural networks, akin to machine translation. Generative chatbots require vast amounts of data and are based on deep neural networks, enabling them to generate responses dynamically based on input.

Here we are aiming to create a retrieval-based chatbot.
To create a retrieval-based chatbot , we typically need the following components:

1. **Intents.json:** This file contains predefined patterns and responses. It helps the chatbot understand user inputs and generate appropriate responses.

2. **train_chatbot.py:** This Python file is used to build the model and train the chatbot. It involves preprocessing the data, creating the model architecture, and training the model using the data from intents.json.

3. **Words.pkl:** This pickle file stores the Python object containing a list of words from the vocabulary used in the chatbot's training data.

4. **Classes.pkl:** Similar to Words.pkl, this pickle file stores the Python object containing a list of categories or classes used in the chatbot's training data.

5. **Chatbot_model.h5:** This is the trained model file that contains information about the model's architecture and the weights of the neurons. It is used to make predictions and generate responses during chatbot interactions.

6. **Chatgui.py (or similar):** This Python script implements a graphical user interface (GUI) for the chatbot, allowing users to interact with the bot easily.

These components work together to create a functional retrieval-based chatbot that can understand user inputs and provide appropriate responses.


 Steps for creating a chatbot in Python (using NLTK , Keras , Pickle)

•	import and load the data file
•	Preprocess data
•	Create training and testing data
•	Build the model
•	Predict the response

**1.	Import and load the data file**

First, we create a file named” train_chatbot.py “. We then import the necessary packages for our chatbot and initialize the variables we will use in our Python project.

The data file is in JSON format so we used the json package to parse the JSON file into Python.

intents.json file will look like this:
 ![image](https://github.com/Ayishwaryaa/SimpleChatBot/assets/112137001/88112b0b-e137-40a3-84b2-6b7750b91c4b)


** 2.	Preprocess data**

Next step is to perform various preprocessing on the text data before we make a machine learning or a deep learning model. Based on the requirements we need to apply various operations to preprocess the data.

**Tokenizing** is the most basic and first thing to do on text data. Tokenizing is the process of breaking the whole text into small parts like words.

Here we iterate through the patterns and tokenize the sentence using nltk.word_tokenize() function and append each word in the words list. We also create a list of classes for our tags.


**3.	Create training and testing data**

Now, we will create the training data in which we will provide the input(pattern) and the output(the class our input pattern belongs to). But the computer doesn’t understand text so we will convert text into numbers.


**4.	 Build the model**

We have our training data ready, now we will build a deep neural network with 3 layers. We use the Keras sequential to build sequential model for this. After training the model for 200 epochs we save the model as ‘chatbot_model.h5’.


**5.	Predict the response**

Let's create a new file ‘chatgui.py’ to predict the sentences and get a response from the trained chatbot and display it to the user

We will load the trained model and then use a GUI(graphical user interface) that will predict the response from the bot. The model will only tell us the class it belongs to, so we will implement some functions which will identify the class and then retrieve us a random response from the list of responses.

We need to import the necessary packages and load the ‘words.pkl’ and ‘classes.pkl’ pickle files

we will use Tkinter library which is shipped with tons of useful libraries for GUI. We will take the input message from the user and then use the helper functions we have created to get the response from the bot and display it on the GUI.


**6.	Run the chatbot**

_Note: The entire source code for this project has been executed solely using Python IDLE. However, it is uncertain whether the code will function properly on other platforms such as Google Colab, Jupyter, or any other Python environments..._


To run the chatbot, we have two main files; train_chatbot.py and chatgui.py.

First, we train the model using the command in the terminal:

**python train_chatbot.py** 

![image](https://github.com/Ayishwaryaa/SimpleChatBot/assets/112137001/32effab2-d789-4724-81f6-5b39a10f52b4)

![image](https://github.com/Ayishwaryaa/SimpleChatBot/assets/112137001/5cdee7c3-5352-4ec1-8c68-85de7c602349)


Then to run the app, we run the second file.

**python chatgui.py**

The program will open up a GUI window within a few seconds. With the GUI we can easily chat with the bot.


This is how the chatbot window looks..
we can see the user inputs and the chatbot responses...
![image](https://github.com/Ayishwaryaa/SimpleChatBot/assets/112137001/27397d8d-705d-4636-afcc-eff3b2f4a449)

