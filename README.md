# CMSC436-Semester-Project

Setting up User API Key:
1) Go to "https://beta.openai.com/account/api-keys" and create an API key - make sure to copy it. 
2) Go to MainActivity.ky and replace the following with your API key:
        return Request.Builder()
            .url("https://api.openai.com/v1/completions")
            .addHeader(
                "Authorization",
                "Bearer INSERT-API-KEY-HERE"
            )
3) Save and Run


Text Suggest

Overview

We are developing an AI tool to assist users in constructing and detailing text messages they want to send. We are targeting this app toward busy users who need to send detailed texts while under time constraints or when they simply need a break from thinking!

The tool just needs two short inputs from the user and will use those to generate a comprehensive list of complete and detailed text messages which the user may use.

App Functionality

This android application is created for the use case of accessible, customizable, and reliable text message suggestions for phone users through utilizing the Generative Pre-trained Transformer 3 (GPT3) autoregressive language model developed by OpenAI. 

When the user needs a quick text suggestion, the application will work as follows:
The user will log in with their credentials in the Login View which will be authenticated with the user's phone number. 
This will make a call against Firebase which will verify the user's identity
The user will see the Input View where they will just need to type two short inputs; a Contact and a Context.
These inputs will be incorporated into the text fields in the following predefined string: 
“Write a suggestion for a text message to [Contact] about [Context].”
All the user inputs will be saved in the History View (which they can access from the Input View). 
The inputted string will be used as an input which will be used to call the GPT3 API model.
The API will read the inputted string and output an AI-generated, human-like text which will be stored temporarily. 
The app will repeat the input call to the API four more times (five total calls) and generate a scrollable list of 5 outputs in the Output View which the user can choose to copy.


Tech Stack and Android System Components (Tentative)

Kotlin (Activity Component, Content Providers)
Firebase
GPT3 API


Views

Login View. This is the screen that will be displayed if the user isn’t logged in yet. It will have input fields for a phone number and password as well as a link to sign up if the user doesn’t have an account yet.

SignUp View. This is the screen that will be displayed for the user to create an account if they don’t already have one. It will have input fields for a phone number and password as well as a link to log in if the user already has an account.

Input View. This is the default screen for a logged-in user. There will be a text box and submit button to send requests for suggestions based on text box content. There will also be a button to view history which will pull up a history tab.

Output View. This view displays a list of output suggestions after an input has been submitted and requests are returned.

History View. This is a view that displays a scrollable list of all previously suggested text messages. The list will contain cards with input from the user and corresponding suggestions.


User Stories

A user can sign up with their phone number and a password
A user can input a contact name and the context of a text message they want to send. They then receive a list of suggestions for what to send
A user can view previous inputs and suggestions 




Risks 

Some project risks that we have identified and ways to address them are:
It may not always produce the best suggestions and the outputted suggestions might be correct. We plan on minimizing this risk by producing a list of five suggestions and letting the user choose which one makes the most sense for them.
GPT3 API has a predefined API rate limit (credit system). We can handle this issue by having multiple OpenAI accounts (one per team member) and that should be plenty of API calls for implementing and testing the project. 

