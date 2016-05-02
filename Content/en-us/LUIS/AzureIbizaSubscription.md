<!-- NavPath: AzureIbizaSubscription
LinkLabel: Azure Ibiza Subscription
Url: LUIS-api/documentation/AzureIbizaSubscription
Weight: 85 -->

#Creating Subscription Keys Via Azure Ibiza

For unlimited traffic to your HTTP endpoint, you must create a metered key for your account on LUIS. Metered keys provide unlimited traffic to your endpoint following a payment plan. To create your key, follow these steps: 

1. Sign in to the Microsoft Azure Portal 
2. Click (+New) and search for “Cognitive Services” in the marketplace, then click on Cognitive Services APIs and follow the create experience to create an API account you are interested in. 

![Ibiza Search](./Images/Ibiza_search.png) 

3. Choose the API you are interested to create a subscription for by clicking on the API Type. In our case, choose the Language Understanding Intelligent Service (LUIS) option. Configure the subscription with settings including account name, pricing tiers, etc. 

![Ibiza API Choice](./Images/Ibiza_apiChoice.png) 

4. Once you have created the API account successfully; you can view the keys generated in the (Settings->Keys) blade. These can be tested in your existing application or by following our Documentation. 

![Ibiza Keys](./Images/Ibiza_keys.png)

You can also explore other API account information in the resource view. Today the portal has an events graph showing API calls, but will add additional information in the future. 
Once you have created your key, you can add it to your account via the application settings dialog, found in any application. 
