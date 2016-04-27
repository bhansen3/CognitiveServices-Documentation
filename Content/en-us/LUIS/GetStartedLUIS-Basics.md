<!-- NavPath: GetStartedLUISbasics
LinkLabel: Get Started With LUIS-Basics
Url: LUIS-api/documentation/GetStartedWithLUIS-Basics
Weight: 100 -->

#Get Started with LUIS: The Basics

LUIS lets you build your applications by using the LUIS web interface. No coding needed other than the ability to interpret and use the returned JSON in your application. It is also possible to use the [LUIS REST API](https://dev.projectoxford.ai/docs/services/56d95961e597ed0f04b76e58/) for automation of applications.

###Using LUIS for the first time

To use LUIS, first make sure that you have an up-to-date version of Microsoft Edge, Internet Explorer or Google Chrome. Go to the home page www.luis.ai and log in. You will see a screen like the one below. 

![GetStarted-with-LUIS](./Images/log_in_2.png)

###Creating your first LUIS Application

All LUIS applications are centered around a domain-specific topic, for example booking of tickets, flights, hotels, rental cars etc. or content related to exercising, tracking fitness efforts and setting goals. You need to decide on a domain-specific topic before you can create your LUIS application. In this case, let's take the example of a virtual travel booking agency application.
In the application, you will bundle together the intents and entities that are important to your task. Two intents relevant to the domain of travel booking are "BookFlight" and "GetWeather". Two entities that are important are "Location" and "DateTime". Once we have identified the intents and entities, we can take an appropriate action, when a user interacts with the application. 

###Step 1: Creating an Application

Click on **My Applications** and then the **New Application** button to create a new application. In the dialog box, name it "TravelAgent". Check that the application culture is set to English. Then click **Add App**. 

![New LUIS Application](./Images/NewApplication.PNG) 

This creates the application and takes you to the LUIS Application Editor.

###Step 2: Adding intents, entities and labels

######Defining Intents and labeling utterances

Next, we will add two intents to the application. At the top left of the menu panel, you will see an area for intents. All applications come with one pre-defined intent, **None**. This will recognize user statements that have nothing to do with the application, for example if someone says "How far is it to the moon". 

Go ahead and click **+** next to **Intents**. You'll see a dialog box appear to add a new intent. Enter the intent name of "BookFlight", and the example command that triggers the intent as "Book flight to Paris". This will look like the screen below. 

Then click **Save**, and the utterance will be presented for labeling. The intent "BookFlight" (just click on it) will be highlighted, and you will see a drop-down with the entities you've defined. 

![Labeling Entents](./Images/BookFlightIntent.PNG)

Click on "Location", and you'll see the word "Seattle" highlighted in yellow, indicating that you've labeled the word "Seattle" as a "Location". Choose whether it is a ToLocation or FromLocation, then click **Submit** to submit this label. 

Next, add a second intent called "GetWeather", with the example "How is the weather in London". Label "London" as a "Location" entity, and click **Submit**.

![Pre-built example](./Images/prebuilt-example.png)

######Defining Entities
  
On the left-hand panel, you will see an option to add entities. We'd like to be able to say what kind of travels we are interested in, and also, for planning purposes, to get an idea of what the weather is like at our travel destination. In order to capture the topic of "location", let's create the entity type: "Location". To do this, click the "**+**" button on the **Entities** bar, and fill in the resulting text entry box for "Location". 

######Hierarchical Entities
  
You now have the ability to define relationships between entities based on hereditary hierarchical patterns. The generic entity acts as the parent and the children are the specific types, or sub-groups, under the parent, yet both share the same characteristics. For example, a generic entity may be called “Location” and the specific children of this parent may be called “ToLocation” and “FromLocation”. “Location”, including its children, has now been transformed from being a generic entity to being a specific entity. The LUIS service can recognize these types when labeling utterances, building models and training them for this entity and its children. 

######Defining Hierarchical Entities
  
Using the “Location” example mentioned above, follow these steps. 

1.	In the Application Editor workspace, find **Entities** in the left-hand menu panel, then click the plus sign.
2.	In the **Add a new Entity** dialog box, type "Location" as the entity name.
3.	Click the plus sign next to the **Entity Children**.
4.	In the text box that appears, type the name of the first child, "ToLocation".
5.	Click the plus sign again to add the second child, “FromLocation”, and so on.
6.	To delete a child, if you made a mistake, click the trash can sign next to the entity child.
7.	When finished, click "**Save**".

![Hierarchical Entities](./Images/ToandFromLocations.PNG)

######Using Bing Entities

Once our app shows a set of travel booking requests, we might want to say something like "Book me a flight to Boston on May 4". This will require understanding date words like the names of the months, for example "May", "June", dates of the month and year and so on. Rather than specifying these by hand, we can use a pre-built entity model called **DateTime**. Click the button for **Prebuilt Entities** and select **DateTime** from the dropdown menu.

![DateTime Pre-built Entities](./Images/Date-timePre-builtEntity.PNG)

######Important Notes

 * You may add up to 10 children types for each parent entity.
 * When adding children, make sure you add them at the same time you are creating the parent entity.
 * To delete an entity with its children, click the entity name at the left-hand panel, and then click "Delete" in the dialog box.

######JSON Response

Below you find an example of the Hierarchical Entities and their children as JSON output. Click "Publish" in the upper left-hand corner of the panel, then click "Update published application". 

1. Set the URL parameter "q" to be your question/utterance, for example, "Book me a flight to Boston on May 4".
2. Hit the "Enter" key or click on the generated URL in the dialog box. 
```
{
  "query": "Book me a flight to Boston on May 4",
  "intents": [
    {
      "intent": "BookFlight",
      "score": 0.979744732
    },
    {
      "intent": "None",
      "score": 0.120113634
    },
    {
      "intent": "GetWeather",
      "score": 9.00356056E-08
    }
  ],
  "entities": [
    {
      "entity": "boston",
      "type": "Location::ToLocation",
      "startIndex": 20,
      "endIndex": 25,
      "score": 0.9935189
    },
    {
      "entity": "may 4",
      "type": "builtin.datetime.date",
      "startIndex": 30,
      "endIndex": 34,
      "resolution": {
        "date": "XXXX-05-04"
      }
    }
  ]
}

```

###Step 3: Seeding the System

Now that we have a set of intents and entities defined, the next step is to provide some more examples of utterances that illustrate these concepts. Click on the **New Utterances** tab at the top of the screen. Type "Book a flight to africa" into the entry box and hit enter. You will see a dropdown box showing the possible intents. Select "BookFlight" and note that "africa" is the location of the flight destinations we want. Click on "africa" and then select "Location" from the dropdown box. 

The system needs to be seeded with several examples of each intent, and several examples of each entity. As an example of a **None** intent, enter "I like chocolate cake". Now think of several more examples of each intent, and enter them. 

The system has now been seeded with enough data to deploy an initial application. That is done by training and publishing a model.

###Step 4: Training

When you "train" a model, LUIS generalizes from the examples you have labeled, and develops code to recognize the relevant intents and entities in the future. Internally, LUIS uses logistic regression classifiers to determine intents, and conditional random fields (CRFs) to determine the entities. The training process results in optimized classifiers and CRFs, referred to as models, that LUIS can use in the future. To do training, just click the **Train** button at the bottom of the page. Training also automatically occurs periodically. 

###Step 5: Publishing a Model

The next step is to deploy the models to an HTTP endpoint that will interpret the sentences we send it. Click the **Publish** button in the upper left-hand corner, and then **Publish web service** in the resulting window. After a couple of moments, you will see a url that makes your models available as a web service. LUIS will look like the below screenshot.

![Publish LUIS app](./Images/publish.png) 

###Summary

You have now built a basic LUIS application.
