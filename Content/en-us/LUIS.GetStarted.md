<!-- 
NavPath: CognitiveServices-Documentation/Content/en-us/
LinkLabel: LUIS Get started
Url: LUIS-API/documentation/LUIS.GetStarted
Weight: 100
-->
#Get started with LUIS

In contrast to applications using Cognitive Services’ other APIs which are created on a development platform such as Visual Studio or Android Studio, LUIS lets you build your applications by using the LUIS web interface. No coding needed other than the ability to interpret and use the returned JSON types in your application.

###Using LUIS for the first time

To use LUIS, first make sure that you have an up-to-date version of Microsoft Edge, Internet Explorer or Google Chrome. Go to the home page, www.luis.ai, and log in. (What is meant? I was never asked) You will see a screen like the one below. 

###Creating your first LUIS Application

All LUIS applications are centered around a domain-specific topic, for example booking of tickets, flights, hotels, rental cars etc. or content related to exercising, tracking fitness efforts and setting goals. You need to decide on a domain-specific topic before you can create your LUIS application. In this case, let's take the example of a news-browsing application.
In the application, you will bundle together the intents and entities that are important to your task. Two intents relevant to the domain of news-browsing are "FindNews" and "SendTo," for sharing stories with friends. Two entities that are important are "Topic" and "Recipient.". Once we have identified the intents and entities, we can take an appropriate action, when a user interacts with the system. 
