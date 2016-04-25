<!-- NavPath: GetStartedLUISbasics
LinkLabel: Get Started With LUIS-Basics
Url: LUIS-api/documentation/GetStartedWithLUIS-Basics
Weight: 100 -->

#Get Started with LUIS: The Basics

LUIS lets you build your applications by using the LUIS web interface. No coding needed other than the ability to interpret and use the returned JSON types in your application. It is also possible to use the [LUIS REST API](https://dev.projectoxford.ai/docs/services/56d95961e597ed0f04b76e58/) for automation of applications.

###Using LUIS for the first time

To use LUIS, first make sure that you have an up-to-date version of Microsoft Edge, Internet Explorer or Google Chrome. Go to the home page www.luis.ai and log in. You will see a screen like the one below. 

![GetStarted-with-LUIS](./Images/log_in_2.png)

###Creating your first LUIS Application

All LUIS applications are centered around a domain-specific topic, for example booking of tickets, flights, hotels, rental cars etc. or content related to exercising, tracking fitness efforts and setting goals. You need to decide on a domain-specific topic before you can create your LUIS application. In this case, let's take the example of a news-browsing application.
In the application, you will bundle together the intents and entities that are important to your task. Two intents relevant to the domain of news-browsing are "FindNews" and "SendTo," for sharing stories with friends. Two entities that are important are "Topic" and "Recipient.". Once we have identified the intents and entities, we can take an appropriate action, when a user interacts with the system. 

###Step 1: Creating an Application

Click on **My Applications** and then the **New Application** button to create a new application. In the dialog box, name it "NewsChat". Check that the application culture is set to English. Then click Add App. This will create the application and take you to the LUIS Application Editor: 

###Step 2: Adding entities, intents, and labels

######Defining Entities
  
On the left-hand panel, you will see an option to add entities. We'd like to be able to say what kind of news we are interested in, and also, for sharing, to say who we'd like to share a story with. In order to capture the notion of a news topic, and a recipient for sharing, let's create two entity types: "Topic" and "Recipient". To do this, click the "**+**" button on the **Entity bar**, and fill in the resulting entry box once for "**Topic**" and once for "**Recipient**". 

######Hierarchical Entities
  
You now have the ability to define relationships between entities based on hereditary hierarchical patterns. The generic entity acts as the parent and the children are the specific types, or sub-groups, under the parent, yet both share the same characteristics. For example, a generic entity may be called “Date” and the specific children of this parent may be called “StartDate” and “EndDate”. “Date”, including its children, has now been transformed from being a generic entity to being a specific entity. The LUIS service can recognize these types when labeling utterances, building models and training them for this entity and its children. 

######Defining Hierarchical Entities
  
Using the “Date” example mentioned above, follow these steps. 

1.	In the Application Editor workspace, find **Entities** in the left-hand menu panel, then click the plus sign.
2.	In the **Add a new Entity** dialog box, type "Date" as the entity name.
3.	Click the plus sign next to the **Entity Children**.
4.	In the text box that appears, type the name of the first child, "StartDate".
5.	Click the plus sign again to add the second child, “EndDate”, and so on.
6.	To delete a child, if you made a mistake, click the trash can sign next to the entity child.
7.	When finished, click "**Save**".

![Hierarchical Entities](./Images/AuthoringHierarchicalEntities.jpg)

######Labeling Children
  
1.Type any utterance like “Find news about Obama publish from 12 July 2014 till 12 August 2014”
2.Mark the entity “12 July 2014”, click on the arrow  beside the Parent, Date, Entity to display its children.
3.Select the child entity.
4.Submit the utterance.

######Important Notes

 * You may add up to 10 children types for each parent entity.
 * When adding children, make sure you add them at the same time you are creating the parent entity.
 * To delete an entity with its children, click the entity name at the left corner, and then click "Delete" in the dialog box.

######JSON Response

Below you find an example of the Hierarchical Entities and their children as JSON output. Click "Publish" on the left-hand panel, then click "Update published application". 
1. Set the URL parameter "q" to be your question/utterance, for example, "Find news about Paris from 12 July 2014 till 12 August 2015".
2. Hit the "Enter" key or click on the generated URL in the dialog. 

######Using Bing Entities

Once our app shows a set of news stories, we might want to say something like "Read the second one." This will require understanding ordinal words like "first," "second," and so on. Rather than specifying these by hand, we can use a pre-built entity model called "Ordinals". Click the button for "Prebuilt Entities" and select "Ordinals" from the dropdown menu. 

######Defining Intents and labeling utterances

Next, we will add two intents to the application. At the top left of the screen, you will see an area for intents. All applications come with one pre-defined intent, "None". This will recognize user statements that have nothing to do with the application, for example if someone says "How far is it to the moon" to our NewsChat system. 

Go ahead and click **+** next to **Intents**. You'll see a dialog box appear to add a new intent. Enter the intent name of "FindNews", and the example command that triggers the intent as "find news about mars". This will look like the screen below. 



