# Echo-GateKeeper
This skill uses the Twilio API to send a text message to a physical gate which can be controlled via SMS.

# Keywords 
Amazon, Alexa, Echo, Twilio, Rest, AWS, Lambda, Alexa Skill Kit, ASK

# Description
 Echo-Gatekeeper is the implementation of an Amazon AWS Lambda function which enables sending of SMS text messages to a physical gate which can be controlled from authenticated numbers.

 ##Setup
  
1. Create a Twilio account and purchase a number that can send SMS texts to your reciever.
2. Gather your Twilio credentials (accountSid and authToken) as well as your outgoing number.
3. From the Amazon AWS Console (https://aws.amazon.com), create a Lambda function.  Be sure and choose Alexa Skills Kit as the Trigger.
4. Copy the code from the index.js file in this repository into the inline code editor.  
5. Edit the accountSid, authToken, fromNumber, and toNumber and use your collected details.  Complete the lambda function and save.  
6. Take note of your Lambda ARN.
7. Create a new Alexa skill from https://developer.amazon.com/edw/home.html#/skills/list using the Alexa Skill Kit (ASK).
8. Give the skill a name. (I used 'gateKeeper' and 'gate' for invocation) Choose the endpoint to be your previously implemented lambda function by pasting in your ARN id.
9. Use the contents of intents.json for Intent Schema.
10. Use the contents of custom_actions_slot.txt to configure the LIST_OF_ACTIONS slot.
11. Use the contents of sample_utterances.txt to configure utterances.
12. Your skill should be ready without any further configuration.
 
# Usage
Say "Alexa, tell gate to {open|latch|close}". Alexa calls the Lambda function, which calls Twilio, which sends an SMS to the gate with the content of {Action}.