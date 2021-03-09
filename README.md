# Instagram-post-integration-with-Discord
With the Covid-19 pandemic forcing us to embrace online communication more then ever before, organizations are increasingly reliant on social media platforms to engage with their audience.

With Instagram having proven time and again to be a key player in the social media space, and discord emerging as the platform of choice for gamers, as well as acting as a social hub for many community's, I felt it important to create a guide for anyone who would like to automate the process of posting an announcement to their discord server about a recent Instagram post.


## Project goals
To guide a user through the process of sending automated notifications on discord about a new Instagram photo post on their Instagram page.

## Prerequisites 
- ifttt.com account 
- Discord account
- Discord server with appropriate privalages to manage text channels and webhooks 
- Instagram account 
- Basic knolage of how to navigate discord and view server settings.

### Beneficial but not required
- Knowledge of json post method

## Set 1 - Create webhook on Discord server
The first step will be creating the webhood on our discord server. This will be the endpoint of our json post requrest and will alow us to send commands to our discord server that will facilitate an automated post in the relevent test channels. 

To create a webhook, join the relevent server and navagate to the server settings page, location shown below: 

![image](https://user-images.githubusercontent.com/79415636/110516955-22481880-8102-11eb-8d07-c7bd9476b8dd.png)

On the left of the screen you will see a list of server setting catagorys, select "Integrations" from this screen click "New Webhook" and the below will be presented: 

![image](https://user-images.githubusercontent.com/79415636/110517144-61766980-8102-11eb-9290-d53e23ed0023.png)

This is the profile configuration for the profile that will post the anouncment of a new Instagram post. You may edit the profile name, and avatar. You will also use the "CHANNEL" selection to select the text channel where the announcement will be made. I recomend creating an #announcement channel for all relevent postings. 

Once that is created, save relevent changes. We will return to this window later to retreave the "Webhook URL". **NOTE THE WEBHOOK URL MUST BE KEPT CONFIDENTIAL, AS ANY USER WITH THIS LINK CAN POST TO THE CHANNEL, IGNORING PRIVALAGES**

## Set 2 - Create ifttt Applet

To enable us to track when a new post is created on Instagram, we will utalize an ifttt applet. 

Please log into your ifttt account - from here, you can press "Create" on the top left of the screen, as shown below:

![image](https://user-images.githubusercontent.com/79415636/110518478-0ba2c100-8104-11eb-973c-4ac35bf802f5.png)

You will be presented with the below screen: 

![image](https://user-images.githubusercontent.com/79415636/110518842-89ff6300-8104-11eb-935f-75c4fb4e5c2c.png)

From this screen, select "If This". You will be presented with the below: 

![image](https://user-images.githubusercontent.com/79415636/110518902-a13e5080-8104-11eb-983e-1136540f44f4.png)

Please such for "instagram" in the search service field, as shown below:

![image](https://user-images.githubusercontent.com/79415636/110518993-badf9800-8104-11eb-8f45-898715b19d74.png)





