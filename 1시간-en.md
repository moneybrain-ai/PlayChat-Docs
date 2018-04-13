## What kind of Chatbot do you want?

PlayChat chatbots make dialog with the user’s question and the chatbot’s respond as it’s two main message units. PlayChat chatbots can be made using two different methods.

## Chatbots made using dialog sets

This method is used by teaching the chatbot blocks of dialog which are made by consolidating the question and answer into one. It it mostly used to create FAQ Chatbots.

## Chatbots made using dialog scenarios

This method is used by using scenario graphs that are provided by PlayChat to create the chatbot. If a dialog scenario is used, it works beyond simple one-on-one Q&As and can even work dialogs that require specific procedures and functions(C.F. Crawling, Phone num. certification, interlocking external servers, etc.).

## Tip

It is possible to create a chatbot by using both dialog blocks and scenarios, this way a smarter/practical chatbot can me created. It is best if you decide on the method determining on the purpose of your chatbot.

## Setting up chatbots using dialog scenarios

This document presents the procedures of creating a “BitcoinBot” using dialog scenarios. A BitcoinBot is a chatbot used to search information regarding bitcoins.

In order to set up a chatbot using dialog scenarios, a basic unit of dialog(cards) consisting of user inputs and chatbot responses must be created. Dialog scenarios consist of numerous sets of dialog cards, and it is possible to teach a chatbot multiple dialog scenarios.

## Creating a Chatbot

Create a chatbot following these procedures.

1. Sign up if you do not have a PlayChat account, if you do, please log into your account.

2. Choose “Create new bot” -> “Empty Bot” on the chatbot managing page

3. Fill in the blank spaces.

4. Click on “Save”. Once the chatbot is created, it will show up as a card format. Click on the created chatbot.

## Creating a Dialog Card

Dialog scenarios consist of dialog cards made from user inputs and chatbot outputs. If advanced functions are utilized, it is possible to add execution functions before responses.

Create a dialog card following these procedures.

[Watch the example video](https://youtu.be/44QP-8ooqto)

1. Choose “Dialog Scenarios” in the development menu on the navigation bar located on the left of the screen.

2. Choose the “Add” button on the right side of the starter card and name it “Bitcoin Starter”. The name of the card is what the card is called, also known as the identifier.

3. Enter the questions the users may ask in the “User input” space. Since this is a BitcoinBot, enter questions about bitcoins in the user input space. The more questions you add, the more user inputs the chatbot will be able to understand. Enter the following example questions in the user input space. In order to enter multiple user inputs, click on the “+” button next to the user input space.

* Bitcoin

* Coin

4. Enter the correlating responses in the “Chatbot response” space. Enter a question asking what kind of bitcoin is being searched as the response. Enter the following example responses in the chatbot output space. In order to enter multiple chatbot outputs, click on the “+” button next to the chatbot output space.

5. 

* What kind of bitcoin are you searching for?

5. If multiple responses are entered, the program will randomly select a response as the output.

6. Click on the “Save” button.

7. Go for a test drive. Enter the question that was added through the test dialog window on the right. You’ll find the chatbot responding using the ready-made output.

## Tip 
Under the test dialog window, a dialog analysis window will pop up. It provides a simple analysis on the basic units of cards consisting of the user’s input and the chatbot’s output.

* User input analysis - Goes through a natural language processing of the user’s inputs and shows the results.

* Intent analysis - Shows the intent that was matched with the user’s input

* Entity analysis - Shows the entity that was ousted from the user’s input

* Chatbot output analysis - Shows which data was matched with the user’s input to present the chatbot’s response.

## Create a Bitcoin Search Scenario

A dialog scenario is  a set of different card units. Much like the addition of the “Bitcoin Starter” card on the initial starter card, it is possible to add descendent  cards or sister cards. As numerous cards are connected, they form a tree-shaped graph, and the final outcome is called a Dialog scenario.

## Tip 
Why is a dialog scenario needed? Take a look into the procedure of a BitcoinBot gathering info from the users of 1) the type of bitcoin they are about to search 2) the info they are trying to find out and 3)the cases of them executing the search

1. The info regarding the type of bitcoin the user wants to search for is input.

2. The information the user wants to know about is input.

3. The program executes the search.

* If there is no problem with the results of the search, the results are output.

* If there are no results of the search, the program either returns to procedure 1, or procedure 2.

For the chatbot to properly execute it’s cause, the above procedures are made in order. A single card unit may be used to process the entire procedure, but this may not be an ideal case for beginners as it may not be intuitive. This is because, in principle, a single card unit is best used to process a single function. In the case of a “Search Scenario”, three different functions are needed, due to the three procedures above, so it is ideal to connect and utilize three different card units to create a Bitcoin Search Scenario. In other words, when a specific procedure has to be made in order to fulfill a cause, creating descendant cards is recommended.

  
  


Create a bitcoin search scenario following these procedures.

1. Create a “Bitcoin Type” card as the descendant card of the “Bitcoin Starter” card.

* Card Name - Enter type of Bitcoin

* User Input - if(true)

* Chatbot Output - Enter the information you want to know regarding bitcoin.

2. If you enter “if()” in the user input space, the input mode alters. Enter “if(true)”. In the case of “if()”, it means the card will be executed no matter what the user input is. It includes some Java Script coding. If you enter “True” in between the colons, the select case will always be executed.

3. Create a “Search Information” card as the descendant card of the “Bitcoin Type” card.

* Card Name - Enter information to search

* User Input - if(true)

* Chatbot Output - Would you like to go on with the search?

4. Create an “Execute Search” card as the descendant card of the “Search Information” card.

* Card Name - Execute search

* User Input - Execute

* Chatbot Output - The search results for bitcoins are as the following.

5. Go for a test drive.

* “Bitcoin Starter” card - > Once the user enters “Bitcoin Start”, the chatbot will respond by asking the user to input the type of bitcoin the user wants to search

* “Bitcoin Type” card -> The chatbot will respond by asking the user to input the information the user wants to search.

* “Search Information” card -> The chatbot will resbond by asking the user if they want to make the search

* “Execute Search” card -> Once the user confirms the execution, the chatbot will output the results of the search.

A basic dialog scenario used to search info on bitcoins has been made. Now, take a look through the procedure of teaching the chatbot to request website info from the user after it has been given a faulty input.

## Round Off

So far, we’ve seen the procedures used to set up chatbots using dialog scenarios. Chatbots using dialog scenarios connect different card units in order to function for a specific cause. However, for a chatbot to actually search for bitcoins, you must add “Execution functions pre-output”. In the next document(applying “Execution functions pre-output”), you’ll learn to fulfill this part of setting up the chatbot.

## Applying “Execution functions pre-output”

Execution functions pre-output is used when the chatbot requires external resources(Bitcoin prices, Weather info, Box Office info, etc.), or when a certain level of coding is needed to manipulate the chatbot. For example, for a BitcoinBot to execute a search, it must save the data of the bitcoin type and the info the user inputs. It also needs a function to execute the search. This document is focused on implementing the function.

## Saving the Variables

To execute the search, the chatbot must save the data of the bitcoin type and the search info from the user input. In order to save the user input data, execution functions are used.

Create execution functions pre-output following these procedures.

1. Double click the “Bitcoin Type” card and open the card editting window.

2. Enter “saveBitcoinName” in the execution functions window and click “Make New Function”.

3. On the newly created function workspace window, add

4. context.session.bitcoinName = dialog.userInput.text;  in the action window of the “saveBitcoinName” workspace. In other words, enter the code.

5. Click on “Save”.

Now the  input from chatbot users(dialog.userInput.text) is saved under context.session.bitcoinName  of the function workspace. If you want to utilize the saved input, you can use it through here(context.session.bitcoinName).

The same goes for making an execution function for the next card unit.

1. Double click the “Search Information” card and open the card editting window.

2. Enter “saveInfo” in the execution functions window and click “Make New Function”.

3. On the newly created function workspace window, add

4. context.session.info = dialog.userInput.text;  in the action window of the “saveInfo” workspace.

5. Click on “Save”.

Now the  input from chatbot users(dialog.userInput.text) is saved under context.session.info  of the function workspace. If you want to utilize the saved input, you can use it through here (context.session.info).

## Using the saved variables

We’ll be using the saved variables stored in context.session.bitcoinName  and context.session.info  to create responses from the chatbot. Edit the “Search Information” card following these procedures.

1. Double click the “Search Information” card and open the card editting window.

2. Enter the following in the chatbot response space.  
Bitcoin Type : +context.session.bitcoinName+  
Search Information : +context.session.info+  
Would you like to go on with the search?  
Texts like “+Variable+” are written in specific language in order to reach the saved variables in the function workspace. Enter the variable you would like to reach in between “++”.

3. Click on “Save”.

4. Go for a test drive.

* Enter “Bitcoin” to start up the chatbot.

* Enter the type of the bitcoin you want to search.

* Enter the information regarding the bitcoin you want to search.

* The chatbot will correctly output the type and the information of the  corresponding bitcoin that the user input.

## Executing the Search

Find out how to create an execute function that executes the search using the saved data from the user input.

Edit the “Execute Search” card following these procedures.

1. Double click the “Execute Search” card and open the card editting window.

2. Enter “searchBitcoin” in the execution functions window and click “Make New Function”.

3. On the newly created function workspace window, add () in the action window of the “searchBitcoin” workspace.

4. Enter “The result of the search are as the following” in the chatbot response space.

5. Results : +context.session.result+ BTC

6. Click on “Save”.

7. Go for a test drive.

* Enter “Bitcoin” to start up the chatbot.

* Enter the type of the bitcoin you want to search.

* Enter the information regarding the bitcoin you want to search.

* Enter “Execute”.

## Round Off

So far, we’ve looked through the procedures of applying execute functions. After creating a functions that saved the data from the user input, an execute function using an external AIP was made to fulfill the chatbot’s objective. If you wish to  look for detailed procedures, please take a look at the general outline documents.
