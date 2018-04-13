## Dialog Scenarios

Dialog scenarios are scenario graphs in the form of trees, and are tools that assist the user to create and edit a chatbot. It is divided into a scenario tab, and a function workspace tab. To use a dialog scenario, click on “Develop” -> “Dialog Scenarios” on the navigation bar.

## Development

## Cards

In the dialog scenario tab, you can see several boxes that are connected. Each one of these boxes are called “Cards”. Each card consists of the card name, user input, and chatbot responses. Double click the card and the card editting tab will appear on the right side.

1. Card Name  
A card name is the name of the card and is used as the identifier and thus can’t be  duplicated or overlapped. Card names are used in the “Dialog flow adjustment” function.

2. User Input  
User input is the part where the input that implements the entire card(or the predicted user input) is specified. For example, if you have entered “Hello” in the user input card, the moment a chatbot user types in “Hello”, the card is executed.

3. Chatbot Response  
Chatbot response is the part where you design the response the chatbot will output once the card is executed. For example, if you have entered “Hello” in the chatbot response card, the chatbot will output “Hello” once the card is executed.

4. Parent Cards, Descendant Cards, and Sister Cards  
“Parent Cards” and “Descendant Cards” used to describe the relation between two cards that are directly connected. A card can have a single parent card and multiple descendant cards. For example, all the cards that are connected to the right side of the starter card are descendant cards which all have the starter card as a parent card. Cards that share the same parent cards are called “Sister Cards”. The basic relations between each card follow the family tree.

5. Depth  
“Depth” refers to the generation of the cards. For example, in the case of the starter card, the generation(or depth) is 0, and the depth of it’s descendant cards are 1. The depth value is added by 1 for each generation that goes down.

6. Cursor  
“Cursor” is a term referring to the card that is currently awaiting the user’s input (or the card that was executed most recently). Once the starter card is executed and is awaiting the user’s input, the cursor is set on the starter card.

* The cursor will move once there is an input from the user.

* The movement of the cursor can also be referred to as the flow of the dialog.

* The flow of the dialog(movement of the cursor) basically moves from parent cards to the descendant cards. However, if the dialog flow adjustment function is utilized, it may move to a different card of a random position.

7. Searching, Matching, and Executing  
  


* “Searching” refers to the act of identifying if the chatbot user’s input concurs with a card’s “user input information”. For example, if a chatbot user types in “Hello”, identifying the card that possesses “Hello” as it’s “user input information” is the act of searching.

* There are orders of sequences in a search. The search starts from the upper descendant cards to the lower descendant cards. In other words, the chatbot judges if the user input matches the first descendant card(the highest card) first, and if unsuccessful, repeats the act on the second descendant card. Because of this, if there are cards that share the same “user input information”, the search will automatically match the user input with the highest card that possesses that info.

* Common cards are searched before general cards. Regardless of the position of the cursor, the search will start with the common cards and then the general cards.

* A “Match” is the discovery of the card with the exact “user input information” as the actual user input. For example, when a chatbot user types in “Hello”, and the program finds the card that has “Hello” as it’s “user input info”, the user input is matched with the very card.

* An “Execution” is when the chatbot successfully outputs a response when the user input is matched with a certain card. For example, when a chatbot user types in “Hello” and it is matched with a card that has the same “user input info”, and the chatbot outputs the concerning card’s response, the card has been successfully executed.

* Once a card is executed, the cursor moves to the concerning card and returns to waiting for the next user input.

8. Dialog Flow  
”Dialog Flow” refers to the movement of the cursor from “Chatbot User’s Input” -> “Search” -> “Execute”.

“Chatbot User’s Input” -> “Search(match sequence)” -> “Execute(chatbot response)” -> “Chatbot User’s Input” -> …

* Chatbot User’s Input

* Search - The program searchs for the card that matches with the user input.

* Execute - Once a card is executed after being matched with the chatbot user’s input, the cursor moves to it’s position. After the chatbot outputs it’s response, it awaits for the user input. (If the chatbot user’s input matches with none of the cards, the chatbot responds “Unable to understand” and the cursor moves to the starter card. This is because there are no descendant card that matches with the user’s input.)

9. Common Cards  
Common cards are the cards that are searched before all other cards. You can identify the common cards by clicking on the “Common Cards” button in the dialog scenario tab. Regardless of the starter card or the position of the cursor, common cards are the first to be searched for a match with the user’s input.

* Common cards are the cards that are executed when the starter card user begins the dialog with the chatbot, and the cards that are executed when the user wishes to return to the beginning of the dialog scenario.

* Common cards are executed when the user types in “Go Back”, in order to return to the previous dialog card. These common cards are created to utilize the “Return to previous dialog” function of the dialog flow adjustment functions.

* Common cards are executed when the user types in “Upper”, in order to return to the parent card of the card that the cursor is currently positioned at. These common cards are created to utilize the “Go to upper card” function of the dialog flow adjustment functions.

* The “No Reply” common card is the card that is executed when there are no matches from a search. The default chatbot response for this card is “Unable to understand”.

10. Menu  
There is a menu available to modify cards on the upper right hand of each card.

* Create a descendant card - Creates a descendant card that has the relevant card as it’s parent card. The newly created descendant card is added as the lowest descendant card. You can also create descendant cards by clicking on the “Add card” button on the right side of each card.

* Move Up/Move Down - Change the order between sister cards.

* Cut card - Delete the relevant card and make a copy of it in the memory of the computer.

* Copy card - Copy the relevant card and make a copy of it in the memory of the computer.

* Paste card - Create by pasting the card copied in the memory as the descendant card of the relevant card.

* Duplicate card - Create a duplicate of the relevant card as it’s sister card.

* Delete card - Delete the relevant card.

## User Input

1. Organization of the User Input

2. The basic mode of all user input are keywords. It is possible to diversely organize user input by associating keywords, intents, entities, “RegExr”s, types, and “If Conditional”s.

* Keyword

* The basic mode of user input are keywords.

* The “Keyword Method” is when the card that is matched with the chatbot user’s input is executed. For example, when a keyword such as “Summer outfit cotton” is set as the keyword info of the card, the chatbot user must input a sentence that uses every single keywork such as “Can you find me a summer outfit made of cotton?” for the card to be executed.  When the keywords are entered into the card info seperately such as “Summer”, “Outfit”, “Cotton”, the chatbot user can type in a sentence that only uses one of those keywords for the card to be executed.

* The “Keyword Method” is appropriate for simple chatbots such as “Button Chatbots’, by is not so for dialog chatbots or advanced chatbots. For example, when a chatbot user inputs “Find me a summer outfit made of cotton”, the keyword method is appropriate, but for different sentences with the same meaning such as “Find me clothes for when it’s hot”, the relevant card will not be executed. In order to process various sentences that share the same  purpose, you must use “Intents” rather than keywords.

* ”Keywords” for “Button Chatbots”! “Intents” for “Dialog Chatbots”!

* Intent(#Intent)

* “Intent” means intention.

* “Find outfits” and “Search outfits” share the same meaning for intent. In this case, you can process both sentences with one intent. Thus, if you set the user input info of a card using intents, it is possible to process various praises and sentences that share the same intent.

* Create an intent from “Management” on the navigation bar -> “Intent”. An “Entry Guide” will appear once you press the ‘#’key while focusing on the user input space of a card.

* Remember the fact that a sentence and an intent are not in a one-on-one relation with each other. In other words, a single sentence can be part of multiple intents. For example, in the case of “I want a jumper”, it can be part of a search intent, or a purchase intent, depending on the context. Much like this, the intent a sentence belongs in may change depending on the context of the dialog. The chatbot developer must keep this fact in mind to use intents consistently.

* Entity(@Entity)

* “Entity” means entity.

* If you want to recognize “t-shirts, pants, skirts, jumpers, etc.” as a single entity(clothing), you can use an “Entity”. The items of clothing will be bundled as an entity named ‘Clothing’. For another example, you may bundle “horses, cats, tigers, etc.” into a different entity named ‘Animals’. In other words, it is possible to bundle separate entities(species) into a bigger, conceptual entity(animals).

* Create an entity from “Management” on the navigation bar -> “Entity”. An “Entry Guide” will appear once you press the ‘@’key while focusing on the user input space of a card.

* Remember the fact that a noun and an entity are not in a one-on-one relation with each other. In other words, a single noun can be part of multiple entities. For example, in the case of “Horse”, it can be part of a “Animals” intent, or a “Chinese Zodiac” intent, depending on the context. Also, the noun “Cat” itself could be an entity and types of cats such as “Siamese Cat” or “Bangol Cat” could be part of the entity. Because of this, you must decide what kind of entity you will use to bundle words, depending on the usage of the word.

* If, in the user input space of the card, the @clothing entity and the #search intent are input with the “AND” condition, the card will only be executed if the chatbot user’s input contain the objects from the @clothing entity and sentences from the #search intent. As a result, it is possible to process various praises such as “find me a t-shirt”, “find me a skirt”, or “search for a skirt” in single card.

* Regular Expression(/RegExr/)

* A ”Regular Expression” is a form used to express “strings in certain patterns”.

* What if you want the chatbot user to input their phone number? If you set the user input info of the card to “010-1234-1234”, this will only match certain phone numbers. However, we can’t enter every single phone number in the user input info. Thus, we need a way to input “a certain pattern of numbers”, which can be solved by using a regular expression.

* Once you save a regular expression that indicates “a certain pattern of strings” such as 010-1234-1234 in the card’s user input info, the dialog card is only executed if the chatbot user types in the pattern. In other words, the card’s user input info is “/^\d{3}-\d{3,4}-\d{4}$/“, so for the card to be executed, the chatbot user must input a  phone number form.

* Enter ‘/‘ in the card’s user input space in order to enter a regular expression. Those who aren’t familiar with regular expressions, please look into [regexr.com](https://www.playchat.ai/moneybrain-ai/PlayChat-Docs/blob/master/regexr.com).

* Type($Type)

* A ”Type” is a form used to express “strings in certain patterns”.

* Types provide the same functions as regular expressions, which read strings in certain patterns. Enter ‘$’ in the user input space of a card to see various types that are already created. Among these types, select “mobile” to receive only the input that are in the form of a phone number. Like this, types basically function so that the program only receives input that are in the form of a certain pattern.(In other words, it works the same way as a regular expression.)

* However, it is possible to accomplish more things with types because unlike regular expressions, types can be manipulated within the function workspace window. For example, you can’t tell whether the  verifying number sent to your mobile phone matches the number the user inputs with a regular expression. A regular expression may be able to read the verifying number that is input by the user, but it can’t tell if it matches the number that is sent to the mobile phone. Thus, you have to approach cases like these with coding, in order to figure out the match. This is when you can utilize types.

* “If” Conditional(IF)

* An “If Conditional” is a function that executes a card with a variable other than the user input info that is already set within the card.

* There are some cases where a card needs to be executed regardless of the input of the chatbot user. For example, when the program must receive a user’s name from the user input, you can’t save or process the data through a certain variable or pattern. This is because there isn’t a stable value or a certain pattern in names(Most Korean names can be catagorized in a pattern so it is possible to use a regular expression or a type). Thus, the card must be executed regardless of the user’s input. This is when you can utilize “if” conditionals.

* To enter an “if” conditional in the input space of a card, you must enter “if()” in the advanced mode and enter the conditional inside the colon.

* The conditional must be written on a code level. The result value of a conditional is either “true” or “false”. If the user input info of the card is set as “if(true)”, the card will always be matched and executed.

* Conditionals may be utilized in a simple method such as the above, but it is possible to use the variables  in the function workspace. For example, if you want to differentiate the matchability between male and female users, you can use the form of “if(gender == ‘male’). Of course, variables such as “gender” and “male” must be  defined in the function workspace beforehand.

2. Add/Delete User Input Information  
Click on ‘+’ to add more user input info, and click on the bin button to delete user input info.

3. Plural User Input Information(“Or” conditional)  
In the user input info of the starter card, there are three default user input info(start,  begin, beginning). If the user’s input is plural, and if any one of the three words are entered, the starter card will be executed. For example, if a user types in any one of ‘start’, ‘begin’, ‘beginning’, the starter card will be executed(you can confirm this in the test dialog window on the right screen).

4. “AND” Conditional of the User Input Information Space  
If plural values are entered into a single user input info of a card, the chatbot user must type in each and every value in order for the card to be executed. For example, if the values “start”, “begin” and “beginning” are entered in the same user input info, the chatbot user must type in “start begin beginning” for the card to be executed.

5. NLU(Natural Language Understanding)  
When a new value is entered into the user input info of a card, a praise that says “nlu” appears under the window in small letters. nlu stands for “Natural Language Understanding”, and is the result of the program translating the value of the user input info into a language the chatbot can understand(natural language processing).

## Execute Functions before Response

“Execute Functions before Response” are functions that process various other functions that are needed before the chatbot outputs a response once the card is executed.

Execute functions are what carries out the various functions needed when a chatbot sends you a text, turns on music, manipulates the household lights, communicates with other machinery or accesses the information of the database. Thus, execute functions require javascript coding, which carries out work that can be done on the coding level.

The javascript code above shows the basic structure of what makes up an execute function.

* Enter in the basic form of “bot.setTask(arg1, arg2);” in the chatbot through the setTask function.

* Enter the name of the function (“myTask”) into the first parameter(arg1) in string format.

* Enter the Object into the second parameter(arg2) in JSON format. The basic structure looks like the following. {

* Implement functions in the function implementation space via javascript coding. Thus, it is possible to use Node.js library.

1. Action Functions

2. Action functions receive three mediation variables: dialog, context, and callback.

* Dialog

* Dialog stores the information regarding the execution of the relevant card(card info, chatbot user’s input, chatbot response) in JSON format. In other words, the dialog parameter(JSON object) holds four keys(card, userInput, output, data).

* “card” holds the information of the card.

* “name” is the name of the card.

* “id” is the identifier of the card.

* “input” are the arrays of values that are saved in the card’s user input information.

* “task” are the execute functions(object) that are registered on the card.

* “output” are the arrays of values that are saved in the card’s chatbot output information.

* “userInput” holds the values and information of the chatbot user’s input.

* “text” refers to the input of the chatbot user itself.

* “nlp” is the array of results that have been natural language translated from the chatbot user’s input.

* “nlpText”  is the string  of values that have been textualized from the results that have been natural language translated from the chatbot user’s input.

* “types” hold the types that been matched with the chatbot user’s input.

* “entities” hold the entities in regard to the chatbot user’s input.

* “intents” hold the intents in regard to the chatbot user’s input.

* “output” holds the chatbot responses about to be output.

* Therefore, if you edit “output”, it is possible to edit chatbot responses on the code level.

* “kind” refers to the kind of  response from the chatbot(Content and Action). Content refers to the basic, normalized chatbot responses(text, image, button), whereas Action refers to the responses from chatbots that utilize dialog flow adjustment.

* “text” refers to the text response of the chatbot.

* “button” refers to the button in the chatbot response.

* “data” is an empty object. It is a “Key” that the chatbot developer may use in order to save and print data.

* A point of caution is that the value saved in dialog.data['key'] = ‘value'; will automatically disappear when the chatbot is updated. Therefore, information that can’t afford to be erased in an update must be saved in context.session['key'] = ‘value’;. Additionally, even if the data is stored in context.session, once the server is rebooted or if interaction is ceased for a while(if a session is expired), the data will disappear. Therefore, data that can’t afford to be erased should be  saved in the database in order to be linked.

* The following is the overall look of a dialog parameter.

* Context

* “Context” holds not only the information related to the execution of a card, but the contextual information regarding the interaction between the chatbot and it’s user in JSON format.  
A “Context” parameter(JSON object) holds three keys(bot, user, session).

* “bot” holds the information about the relevant chatbot.

* “name” is the relevant chatbot’s name.

* “description” is the description of the relevant chatbot.

* “created” is the date of creation of the relevant chatbot.

* “language” is the language the relevant chatbot uses.

* “options” is the basic settings of the relevant chatbot.

* “dialogs” holds the relevant chatbot’s dialog scenario in the format of a JSON object.

* “commonDialogs” hold the relevant chatbot’s common dialog scenario in the format of a JSON object.

* “tasks” hold the execute functions(object) that are registered in the chatbot.

* “types” hold every types that are registered in the chatbot.

* “intents” hold every intent that is registered in the chatbot.

* “entities” hold every entity that is registered in the chatbot.

* “entityContents” hold every entity contents that are registered in the chatbot.

* “dialogsets” hold every dialog sets that are registered in the chatbot.

* “user” holds information on the relevant chatbot’s user.

* “userKey” is the identifier value of the relevant chatbot’s user.

* “channel” holds the information on the channel the chatbot user is using to communicate with the chatbot.

* “session” holds the data regarding the interaction between the chatbot and it’s user, and is where the data that will remain for a certain duration of time(a session) is saved. The duration of a session is 5 minutes, and if there are no interaction between a chatbot and it’s user for 5 minutes, the session will be expired.

* “history” holds the list of cards that were executed in order.

* “dialogCursor” is the identifier value of the card that the cursor is currently positioned at.

* “previousDialogCursor” is the identifier value of the card that the cursor was previously positioned at.

* To save data that will kept for a certain duration of time, context.session[‘key'] = value; is used.

* The following is the overall look of the context parameter.

* Callback

* Execute functions are implemented by Async method, and therefore must summon a callback once the implementation is over. A callback is a function that declares the implementation is over and returns the results. Therefore, carry out a callback() where a function implementation is over.

* callback(arg1, arg2)

* a callback() function can receive two parameters. The first parameter(arg1) is the value which decides on the re-inquiry status. It receives either “true” or “false”. The second parameter(arg2) receives  a sentence of re-inquiry, if the first parameter is “true”. For example, if you type in callback(true, ‘Please repeat.’);, once the execution function is executed the cursor will not move and the chatbot will output “please repeat”. For further examples look into the dialog scenario guide.

2. Plural Action Functions

3. If you want to register a function that utilizes both the preexisting functions and newly implemented additional functions, it is possible to set up plural functions in an action function.

* In the case of “newTask”, it receives arrays through action functions. The elements of the array are Task objects(preTask), pre-registered functions(‘myTask’) or action functions(postAction).

* In a case where an action function is designed as an array, each function will be executed following the orders in the array. In other words, the action function of preTask will be executed, then the action function of ‘myTask’, and finally postAction will be executed.

## Example 1 - Saving a Name

Create an execute function(task) named “saveCustomerName”.

* The javascript code is visible in the function implementation space. Inside context.session.customerName, save the value of dialog.userInput.text . Save the chatbot user’s input(dialog.userInput.text) in a temporary session(context.session.customerName).

* For the relevant value(context.session.customerName) to be output in a chatbot response, enter in the form of “+VariableName+”. For example, if you enter “+context.session.customerName+”, the chatbot will output the relevant value as it’s response.

## Example 2 - Requesting External Servers (Crawling)

For the chatbot to fulfill various functions, it must utilize information from external servers. In order the use info from external servers, create a function with the name of “crawling”. Then, in order to request external servers, use “request.js” and “cheerio(Node.js Module)”.

Add the following code into the function implementation workspace of the “crawling” execute function.

* Enter “+context.session.crawlingResult+” into the chatbot response information for the chatbot to output the relevant value as it’s response.

## Example 3 - Requesting External Servers 2 (API)

Create an execute function named “naverMovieSearch”. Then enter the following code in the function implementation workspace.

* This function is used to search movies on Naver.

* Access [https://developers.naver.com에](https://developers.naver.xn--com-568n/) to register application and receive the values for “client_id” and “client_secret”. Then add “Search” in the API settings. After that, go to Documents -> Service API -> Search -> Movies to look up the information regarding API  summoning.

* The format of information received from Naver is in JSON. More than 10 films are held in arrays in the received data. In order to express array formats in a chatbot response, use grammar such as ###. Detailed explanations will be made in the “Chatbot Response” part of the document.

## Chatbot Response

1. Formation of a chatbot response  
In the default chatbot response of a starter card, along with the chatbot’s greetings is a self-introduction as well.

* If you want the chatbot to respond in the form of text, enter in text, for a more lively brand image, use images.

* In order to simplify the users’ input process, you may add “buttons” on cards. In the case of buttons, it could be a button for a simple answer, but by adding URLs, it is possible to create “Link Buttons” as well.

* “Dialog Flow Adjustment” is a function that has to do with the settings of the cursor’s movement. The cursor ordinarily moves from the parent card to it’s descendant card. You can use “Dialog Flow Adjustment” to move the cursor to a random card.

2. Add/Delete Chatbot Response Information  
Click on ‘+’ to add chatbot response information, and click on the bin button to delete them.

3. Multiple Chatbot Responses(OR Conditional)  
If there are multiple chatbot responses that are set up, any one of them will be randomly chosen as the response.

4. Accessing Variables  
Chatbot responses may stay unchanging, but in a lot of cases, must output different responses depending on who the client is. For example, even if the user has already typed in their name, there may be a need for the chatbot to mention the user’s name in a response. Therefore, you have saved the user’s input data from the username dialog card in a variable(context.session.customerName). If you want to use a saved variable in a chatbot response, enter “+VariableName+”.

* If the object variable is an object, you can access the value of the relevant key using a “.key” form, much like javascript.

* Cf.) +context.session.movieDataObject.date+

* If the array variable is an array, using grammar such as ### can get you access to the array like a “for” conditional. For example, “context.session.movieDataArray” is an array. In this case, use the form of “#movieDataArray#” to get you access to each item in the array. From behind that point it is possible to access the value of each item through the key. When an access of an item is over, add ‘#’ to confirm it is over. Conclusively, it is used in the form of “#array#each item#.

5. IF Conditional (Conditional Chatbot Response)  
We looked at the usage of the “if” conditional at the user input document. The same function can be utilized in chatbot responses. Instead of randomly choosing one response to output, when multiple responses are entered and an “if” conditional is used, the response that corresponds to the conditional is executed. This structure is related to distribution channels. In order to distribute various channels such as Kakao, Facebook, and Naver TalkTalk from a single chatbot, the chatbot must be programmed to fit the form that matches each channel. For example,

6. IF(context.user.channel.name == ‘kakao’) /  
IF(context.user.channel.name == ‘facebook’) /  
IF(context.user.channel.name == ‘navertalk’)  
like the above, the chatbot response must differ depending on the distribution channel.

7. Dialog Flow Adjustment  
The cursor movement in a dialog scenario generally moves from the parent card to it’s descendant card. “Dialog Flow Adjustment” is the function to move the cursor to any certain card.

* Dialog movement

* Move the cursor to a certain dialog card. After the movement, the execute function of the card will be executed and the text output from the previous card will be printed. The cursor will be positioned at the dialog card it moved to.

* Re-Inquiry

* “Re-Inquiry” is a function where the cursor does not move in order to re-execute the chatbot’s response, because there a match from any card with the user’s input is non-existent. In this case, the chatbot will output “Unable to understand”. But if the lowest descendant card’s user input info is set up as “if(true)” and the chatbot response info as “Re-Inquiry”, the cursor will stay at the card of the unanswered question, in the case of a non-existent match. It will then print the relevant card’s chatbot response text info. Like this, the function of “Re-inquiry” is used together with “if(true” in the user input space of the lowest descendant card.

* Move to Previous Dialog

* “Move to previous dialog” is when the cursor moves back to the card that was previously executed, in the case the user types in “previous” in a dialog. This function is implemented with common dialog scenario function. A point of caution: If a card that already uses the “move to previous dialog” function is the previously executed card, this order will cause the cursor to move up two generations.

* Dialog Movement and Search

* “Dialog movement and search” is the function of searching the relevant card’s descendant cards, after the cursor’s movement to the said card. If there is a user input match amongst the descendant cards, it will be executed and if there isn’t a match, the response will be “Unable to understand”.

* Dialog Movement to Return to / Returning

* ” Dialog movement to return to” works the same way as dialog movement. However, if the return function is executed after the cursor is moved elsewhere, the cursor will move back to the parent card of the card where the “Dialog movement to return to” was executed.

## Keyboard Shortcuts

1. Dialog Scenario

* ←  ↓  ↑  → : Move card focus

* Ctrl + ↑  ↓ : Move card up/down

* Enter : Open card edit window

* Esc : Close card edit window

* Insert : Add descendant card

* Del : Delete card

* Space : Fold/open descendant card

2. Card Editing Window

* Tab : Input Switch (User input info, execute functions, chatbot response info, etc.)

* Ctrl+Enter : Save card edit window

3. Function Workspace

* Ctrl + F : Search

* Ctrl + G : Search constantly with the following

* Ctrl + S : Save

4. Common to All

* ? : keyboard shortcut help

## Management

1. Dialog Scenario

2. Files regarding dialog scenarios are basically one of two types( *.graph.js  , *.js ).

* (*.graph.js) file - This is the file that saves the dialog scenario graph in a JSON object form. It is possible to make multiple dialog scenario graph files on the dialog scenario management menu. If there are multiple dialog scenario graph files, each dialog scenario will be bundled as a descendant card of the starter card, for which you can set up priorities among the scenarios.

* (*.js) file - This is the file that sets up execute functions. It is possible to make multiple execute function files on the dialog scenario management menu.

2. Entity

3. This is the menu where you can create, edit or delete an entity.

* Click “upload” to register an entity with an excel file.

* Be sure to check the format of the excel file, if registered as an entity. The format can be downloaded by clicking on the “upload” button.

3. Intent

4. This is the menu where you can create, edit or delete an intent.

* Click “upload” to register an intent with an excel file.

* Be sure to check the format of the excel file, if registered as an intent. The format can be downloaded by clicking on the “upload” button.

4. Task

5. This is the menu where you can create, edit or delete a task.
