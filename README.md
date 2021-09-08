# Chatbot-for-Drug-Recommendation
datasets 
https://drive.google.com/drive/folders/1gxovy0LBSvNzXbWuPvZL_kH5dgAUzFUp?usp=sharing





 DETAILED ARCHITECTURE	

![image](https://user-images.githubusercontent.com/72460414/132449367-0596d332-7f4d-46e5-a28e-6e788e4a77f2.png)


 EXPLANATION OF THE ARCHITECTURE	
 
Input Symptoms

The input symptoms are the symptoms which the user provides the model in order to get the appropriate drug recommended along with the corresponding side effects.

Drug Prediction Model

The disease prediction model is a probabilistic model which will give the predictions based on the symptoms. For this purpose, we are using the Disease-Symptom Knowledge Database which has over 149 unique diseases mapped with 405 symptoms. For accurately predicting the diseases, we have experimented with multiple approaches in our project. This is because the dataset has only one feature that is the symptoms and hence training any classifier with one data point makes it weak which in turn hampers the prediction rate for different inputs. The solution is to try and create multiple data points for the same disease by taking into account all the symptoms present for that disease, their importance and their occurance. Since we cannot say for sure which method will be well suited for this kind of dataset, we have implemented 4 different approaches and all of them focus on a different way of prediction. In the end, all these approaches are trained on 4 classifiers and the accuracies and prediction results are compared for choosing the best possible way.

Drug Review sentiment analysis model

Upon obtaining the most probable diseases the next task is to map the list of drugs that can be prescribed for this particular disease using the Merged Dataset which has been created by preprocessing the symptoms and the drug review dataset. Once we obtain the list of possible drugs the next task is to be able to recommend the best drug for the patient. In accordance we adopted two different approaches for this. First one is a NLP based approach to analyze the sentiments using a neural net model in order to obtain positive or negative sentiment predictions for the reviews. In the second approach we have used the VADER tool. It is a simple rule based model for general sentiment analysis. 

Drug Recommendation model

After the disease has been predicted, we need to recommend a drug for that disease.
For recommendation of the drug, we have used the UCI Machine Learning Repository for Drug
Review dataset which has the disease along with its multiple available drugs, their reviews,
ratings and useful count.This dataset, after preprocessing, is merged with the Disease-Symptom Knowledge Database
There are 6 features in this merged dataset out of which 3 are the ones that will help us to
recommend the best drug.

These 3 features and their importance is explained below:

● Feature 1. Review:

The review column is one of the most important columns for drug recommendation as it
is a direct feedback from the users after using that particular drug. Hence, by doing
Sentiment Analysis, we have taken into consideration only the reviews with a positive
sentiment.

● Feature 2 & 3. Rating & Useful Count:

Every drug has a rating associated with it from 1-10 and a useful count which tells us
how many users have given that particular rating. This information can be used to find a
weighted average rating for each drug.


List of recommended drugs

Final output is what the end user gets is the list of best drugs along with the side effects based on the rating average calculated.


Demonstration
Using the ChatterBot, chatbotAI, chatterbot-corpus, flash ngrok library of python we have implemented a basic chat bot which describes the flow and results of our project in a better way. A chatbot a.k.a. chatterbot, is like a computer program or essentially an AI which can conduct a conversation via text based methods. They often simulate human dialogues and conversations. Popular real life examples include SIRI, Cortana. There are various templates freely available for chatbot and one of them has been used here.
● For designing the UI, HTML, CSS and JavaScript technologies are used.
● Using Ngrok, which allows us to host web pages on localhost, we have hosted this chatbot.
To execute this chatbot on your system, there are two techniques:
1. Using JupyterNotebook on a local machine.
If using this option, just click on the first link shown in the diagram above.2. Using Google Colab.If using Google Colab, or any other medium, use the second link (ngrok.io) as shown above.However, irrespective of the platform, the ngrock.io link will always work. After the chatbot has been executed, use the below steps and text for correct output.
1. Firstly, enter this message: “I am suffering from a cough,decreased body weight,and dyspnea.”
2. After getting response from chatbot, enter this message: “What medicines should i take for bronchitis”
3. Lastly, after getting the recommended drug, enter this message “Are there any side effects for it ?”.
● Below shown screenshot shows these steps and the output of chatbot:
![image](https://user-images.githubusercontent.com/72460414/132449464-d99079c3-8263-4ff9-95ab-62a2d5ca1bfb.png)


As mentioned earlier, this chatbot is very primitive and only programmed for a fixed set of commands. The only purpose it serves is that it provides the flow of our project. The template for this UI is available freely for use.






