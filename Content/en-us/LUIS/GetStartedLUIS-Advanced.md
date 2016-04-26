<!-- NavPath: GetStartedLUISAdvanced
LinkLabel: Get Started With LUIS-Advanced
Url: LUIS-api/documentation/GetStartedWithLUIS-Advanced
Weight: 100 -->

#Get Started with LUIS: Advanced Features

######Adding advanced features to your basic LUIS application

###Action Binding

Once a developer creates one or more entities, and starts creating intents. He/she can link this intent to an action and specifies requirements for these actions to be triggered. These requirements are known as parameters. LUIS supports only one action per intent. Each action can include a group of parameters derived from entities. The parameter can be optional or required, LUIS assumes that an action is triggered only when all the required parameters are filled. 

###Defining an Action

1. On the Application Editor page, on the left-hand panel, click an existing intent or create a new one, for example "FindNews".
2. In the "Add a new intent" dialog box, click "Add Action".
3. Let us say this action requires three parameters, "Publication Date", “Subject” & “Publisher”.
4. Click "Add Parameter". Type the name of the parameter, for example "Publication Date", and specify its type from the entities in the "Type" drop-down. In this case "Datetime" is the entity. 
5. Click "Add Parameter" again to add the next parameter. Let it be "Subject" with "Topic" being the entity.
6. Add a third parameter "Publisher" with "Name" being the entity.
7. Check the "Required" check box next to the name of the parameter that is required for the action to trigger.

Notes:

To delete a parameter, click on the trashcan next to its field. To delete an action with its parameters, click "Delete Action" from inside the "Add a new intent" dialog box.

###Dialog Support (Preview)

LUIS allows you to add conversational interfaces to your applications through a new powerful dialog engine. You can author and  execute your dialog in just a few steps. For example, if the user is searching for news about “The Financial crisis”, and typed an utterance without specifying one of the require parameter, "Publication Date", the system consequently will surface a prompt question saying "Could you please specify the required publication date?”. Let’s see below how you can build and consume this feature. 

After defining all the parameters needed for actions triggering, you now have the ability to add a prompt question to be surfaced, if any of the required parameters is missing. and this where the dialog comes in. 

###Dialog Authoring

1. Click "Go to Preview", and then click "FindNews" intent in the upper left-hand panel. In the "Add a new intent" dialog box, all parameters previously listed in the "Production" mode will be displayed. Note: To return to the "Production" mode, click "Back to Production" at the top. 
2. Select the "Required" check box next to the name of the parameter that must be available for the action to be triggered. In this way, questions will be prompted when users issue queries that do not include the required parameter. 
3. Specify the parameter value from the phrase lists in the "Value" drop-down list.
 Notes: ◦Phrase lists are not used with pre-built entities.
◦ Phrase lists work with parameters the same way they work with utterances; they are considered features to improve the detection accuracy of parameters in the utterances. 

4. In the **Prompt** text box, type the question to be surfaced when the required parameter is missing. 
5. Use the up and down arrows to define the order in which your application will ask these questions. 
6. Click **Save**. 

![Adding prompts](./Images/AddingPrompts.PNG)

###Dialog Execution

Testing with query like "Find News". Here is the JSON response extract for the dialog response: 

```
        "dialog": 
  {
    "prompt": "About What?",
    "parameterName": "FindNews::Subject",
    "contextId": "09629512-7310-4a9d-9411-57e1d7f8022b",
    "status": "Question"
  }
```
Notes: 
A new dialog section appears at the end of the JSON response. 
Only the top scoring intent is returned in JSON response.


To continue the dialog, append the answer to the question along with the contextID as request parameters.Example: &q=financial crisis &contextId= a144a208-2f1f-4faf-877b-8898ec523022 

Here is the JSON repsonse for the following Dialog question: 
```
    "dialog":  
 {
    "prompt": "Can you please specify a publication date?",
    "parameterName": "FindNews::PublicationDate",
    "contextId": "2e48c7e0-d343-465f-ab0d-03a7598b655f",
    "status": "Question"
  }
```
