These are the steps for creation of a basic chatbot using Microsoft Azure services.

1) Accessing your Azure subscription and choosing your service plan.(In my case, Free trial is used)

2) Access language resource and deploy the resource.

3) After deployment, Access the language studio where you will redirected to a different page where you need to fill in details for resource group, subscription as well as language resource created and a storage account.
Note: Ensure that you store all resources within one resource group as this will lead to easy deletion of all the resources together.
To create a resource group, Folow the same steps as the one followed for language service.

4) In the language studio, One must first configure his/her service on the type to be used.
I have used question answer pairing and uploaded a knowledge base using the url given at the end of the notepad.
NOTE : A KNOWLEDGE BASE WILL INDICATE THE LIMIT OF THE CHATBOT

5) Once you deploy the knowledge base, It would prompt you to go and create a chatbot which you can create using the same credentials used for language service with an addition to enter the key that is generated by language service in the keys section.

6) Once you do that, Then you can implement the chatbot and do a demo of web chat with the bot on Azure portal.

7) However for using it as a bot on an individual web page, You need to locate the app service editor located in the app service of the bot which is used to manage the chatbot.

8) Once you locate the app service, You need to locate the app service editor and create a new test.html file under wwwroot folder and paste the code i.e
<iframe src='https://webchat.botframework.com/embed/azurechatbottestlang1-bot?s=YOUR_SECRET_HERE'  style='min-width: 400px; width: 100%; min-height: 500px;'></iframe>

This code can be found under the bot resource-> channels -> web chat -> default site.

Once you paste the code, You need to paste your secret key in the code where its says "YOUR_SECRET_HERE" and save it.

9) Once all these operations are done, You can then open the app service of the chatbot and under overview you can click on default domain which sends us to the site where the bot is functional.
To access our bot just add /test.html to the site url and you are good to go.

10) However if you want to enable speech, Then copy the file "speech.html" to the wwwroot folder and save it.
Once that has been done, You can then access the same like the test.html.
However, You would require the key that is generated by chatbot under web chat to access the speech.html such as 
Site url + /speech.html?s="The key that you generated" and it would work just fine.


https://learn.microsoft.com/en-us/azure/bot-service/bot-service-resources-bot-framework-faq

This link is necessary for creating knowledge base in language service in the create source -> URL -> Then type in this ink in URL link and name -> Azure Bot framework FQA 
You can create your own knowledge base by manual entry and also add follow up questions or prompts to it.
