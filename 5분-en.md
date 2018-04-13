
## What kind of Chatbot do you want

PlayChat chatbots makes dialog with the user’s question and the chatbot’s respond as it’s two main message units. PlayChat chatbots can be made using two different methods.

## Making Chatbots usindialoset

This method is used by teaching the chatbot blocks of dialog which are made by consolidating the question and answer into one. It it mostly used to create FAQ Chatbots.

## Making Chatbots made usindialoscenario

This method is used by using scenario graphs that are provided by PlayChat to create the chatbot. If a dialog scenario is used, it works beyond simple one-on-one Q&As and can even work dialogs that require specific procedures and functions(C.F. Crawling, Phone num. certification, interlocking external servers, etc.).

## Ti

It is possible to create a chatbot by using both dialog blocks and scenarios, this way a smarter/practical chatbot can me created. It is best if you decide on the method determining on the purpose of your chatbot.

## Setting up Chatbots usindialoblock

This document presents the procedures of setting up a chatbot using dialog blocks. “Company introduction chatbots” are chatbots that provide info on basic facts about a company, such as the name, contact info, nature of business, and location.

In order to set up a chatbot using dialog blocks, you must teach the program blocks of data consisting of questions and answers. Dialog blocks consist of numeral sets of these data blocks. It is possible to teach the chatbot multiple dialog blocks.

## Creating a Chatbo

Create a chatbot following these procedures.

<![if !supportLists]>1. <![endif]>Sign up if you do not have a PlayChat account, if you do, please log into your account.

<![if !supportLists]>2. <![endif]>Choose “Create new bot” -> “Empty Bot” on the chatbot managing page

<![if !supportLists]>3. <![endif]>Fill in the blank spaces.

<![if !supportLists]>4. <![endif]>Click on “Save”. Once the chatbot is created, it will show up as a card format. Click on the created chatbot.

## TeachinDialoBlock

Dialog blocks are basically a one-on-one connection method used to link a single question and it’s answer, but it is possible to connect multiple questions to multiple answers as well.

Teach the program dialog blocks following these procedures.

<![if !supportLists]>1. <![endif]>Choose “Dialog Blocks” in the development menu on the navigation bar located on the left of the screen.

<![if !supportLists]>2. <![endif]>Enter the questions the users may ask in the “User input” space. Enter the correlating responses in the “Chatbot response” space.

<![if !supportLists]>◦ <![endif]>User Input - “Where is the company located?"

<![if !supportLists]>◦ <![endif]>Chatbot Response - "PlayChat is located at Hongwu Building, near the 6th exit of gangnam station”

<![if !supportLists]>3. <![endif]>Click on the “Save” button.

<![if !supportLists]>4. <![endif]>Go for a test drive.  
Now the chatbot is ready to understand the given questions and correctly answer them. Enter the question that was added through the test dialog window on the right. Try asking the question using slightly different expressions. PlayChat can answer questions that are similar to the initially added question.

## Ti

Under the test dialog window, a dialog analysis window will pop up. It provides a simple analysis on the basic units of dialog consisting of the user’s input and the chatbot’s output.

<![if !supportLists]>• <![endif]>User input analysis - Goes through a natural language processing of the user’s inputs and shows the results.

<![if !supportLists]>• <![endif]>Chatbot output analysis - Shows which data was matched with the user’s input to present the chatbot’s response.

## Teaching multiple-connecteDialoBlock

It is possible to teach the program dialog blocks which connect multiple questions and multiple answers.

<![if !supportLists]>1. <![endif]>Enter the questions the users may ask in the “User Input” space. Press the “+” key in the “User Input” space in order to enter extra questions.

<![if !supportLists]>◦ <![endif]>User Input - “What is the phone number?", “I want to know the phone number", “Curious about the phone number.”

<![if !supportLists]>2. <![endif]>Enter the correlating responses in the “Chatbot response” space. Press the “+” key in the “Chatbot response” space in order to enter extra responses.

<![if !supportLists]>◦ <![endif]>Chatbot response - “The phone number is 080-858-5683.”, “It’s 080-858-5683~ Give us a call anytime!”

<![if !supportLists]>3. <![endif]>Click on the “Save” button.

<![if !supportLists]>4. <![endif]>Go for a test drive.  
Enter the newly added questions in the test dialog window on the right. If multiple questions were added in a single dialog block, those questions will be processed as one dialog block.  
If multiple responses were added in a single dialog block, the program will randomly choose any one of the multiple responses when a user’s input matches the dialog block.

## Calling iDialoSet

You may teach the program by manually entering each dialog block, but it is also possible to call in ‘Dialog Sets(Multiple dialog blocks)’ at once to teach the program.

## Warning

The file must be in the “Microsoft Excel” format and a certain form must be kept in order to call it in.

Teach the program dialog sets following these procedures.

<![if !supportLists]>1. <![endif]>Choose “Dialog Sets” in the managing menu located on the navigation bars on the left of the screen.

<![if !supportLists]>2. <![endif]>Click on the “upload” button and fill in the empty spaces.

<![if !supportLists]>3. <![endif]>Download the given form, and enter the data in a fitting way to the given form(Question Row - Question, Answer Row - Answer).

<![if !supportLists]>4. <![endif]>Click on the “Choose file” button to upload the file.

## Ti

The uploaded file will be saved as a dialog set. Newly added dialog sets are applied only when you choose to “Use” them.

## Round of

So far, we’ve seen the procedures used to create chatbots using dialog sets. Chatbots made from dialog sets can be used as FAQ functioning chatbots answering large numbers of questions, and can function even more precisely and sensitively, if advanced functions are correctly utilized. In the next document(Setting up chatbots using dialog scenarios), we’ll be taking a look at the procedures used to create chatbots that make dialog that require specific procedures and functions.
