# Instagram-post-integration-with-Discord
With the Covid-19 pandemic forcing us to embrace online communication more than ever before, organizations are increasingly reliant on social media platforms to engage with their audience.

With Instagram having proven time and time again to be a key player in the social media space, and discord emerging as the platform of choice for gamers, as well as acting as a social hub for many communities, I felt it was important to create a guide for anyone who would like to automate the process of posting an announcement to their discord server about a recent Instagram post.


## Project goals
To guide a user through the process of sending automated notifications on discord about a new Instagram photo post on their Instagram page.

## Prerequisites 
- ifttt.com account 
- Discord account
- Discord server with appropriate privalages to manage text channels and webhooks 
- Instagram account 
- Basic knowledge on how to navigate discord and view server settings.

### Beneficial but not required
- Knowledge of json post method

## Set 1 - Create webhook on Discord server
The first step will be creating the webhook on our discord server. This will be the endpoint of our json post requrest and will alow us to send commands to our discord server that will facilitate an automated post in the relevent text channels. 

To create a webhook, join the relevent server and navagate to the server settings page, location shown below: 

![image](https://user-images.githubusercontent.com/79415636/110516955-22481880-8102-11eb-8d07-c7bd9476b8dd.png)

On the left of the screen you will see a list of server setting catagories, select "Integrations" from this screen then click "New Webhook" and the below will be presented: 

![image](https://user-images.githubusercontent.com/79415636/110517144-61766980-8102-11eb-9290-d53e23ed0023.png)

This is the profile configuration for the profile that will post the anouncment of a new Instagram post. You may edit the profile name, and avatar. You will also use the "CHANNEL" selection to select the text channel where the announcement will be made. I recommend creating an #announcement channel for all relevent postings. 

Once that is created, save relevent changes. We will return to this window later to retreave the "Webhook URL". **NOTE THE WEBHOOK URL MUST BE KEPT CONFIDENTIAL, AS ANY USER WITH THIS LINK CAN POST TO THE CHANNEL, IGNORING PRIVALAGES**

## Set 2 - Create ifttt Applet

To enable us to track when a new post is created on Instagram, we will utalize an ifttt applet. 

Please log into your ifttt account - from here, you can press "Create" on the top left of the screen, as shown below:

![image](https://user-images.githubusercontent.com/79415636/110518478-0ba2c100-8104-11eb-973c-4ac35bf802f5.png)

You will be presented with the screen below: 

![image](https://user-images.githubusercontent.com/79415636/110518842-89ff6300-8104-11eb-935f-75c4fb4e5c2c.png)

From this screen, select "If This". You will be presented with below: 

![image](https://user-images.githubusercontent.com/79415636/110518902-a13e5080-8104-11eb-983e-1136540f44f4.png)

Please search for "instagram" in the search service field, as shown below:

![image](https://user-images.githubusercontent.com/79415636/110518993-badf9800-8104-11eb-8f45-898715b19d74.png)

Upon clicking the instagram logo, you will be presented with the "Choose a trigger" , click "Any new photo by you" as below: 

![image](https://user-images.githubusercontent.com/79415636/110519437-3a6d6700-8105-11eb-863f-cb2009b0c8eb.png)

At this point you will be asked to sign into your instagram account, please do so.

Once compleated, you will be sent back to the "create your own" screen, from here please click "*then that*" 

From here you will chose another service, please input "webhook" as below:

![image](https://user-images.githubusercontent.com/79415636/110519779-9f28c180-8105-11eb-89e2-16fb57f1f776.png)

Please select the "Make a web request" option. you will then be presented with the screen below: 

![image](https://user-images.githubusercontent.com/79415636/110520038-e44cf380-8105-11eb-9164-41c66f230564.png)

Please leave this screen open, and return to Discord. 

## Step 3 - Retrive and modify webhook

Return to the integrations section on discord and open your webhooks. Your webhook should be saved here, click on it and press "Copy Webhook URL"

Before we paste it into the appropriate location, we will need to modify this link to ensure it runs correctly.

To modify this link, simply paste it into a word processer of your choice and make the following change:

Replace the 

```
discord.com
```
with

```
discord-ifttt.now.sh
```

This will ensure the webhook will work correctly. More info can be found on https://discord-ifttt.now.sh/.

## Step 4 - Create webhook request

Once you have modified your webhook URL, return to your ifttt page and paste the **full modified link** into the url section. Please ensure not spaces or any other modification then the one noted above are present, else the link will not work.

Once created, select "POST" from the Method section and "application/json" from the Content Type section, as shown below:

![image](https://user-images.githubusercontent.com/79415636/110521556-c97b7e80-8107-11eb-8070-aa5fd2c0aeff.png)

Once you have compleated the above, past the blow code into the "Body" section as shown: 

```
{ "content" : "Hi All, Check out our new post on Instagram below!!\r\r{{Url}}\r\r{{Caption}}\r\r {{SourceUrl}}"
}
```

![image](https://user-images.githubusercontent.com/79415636/110521692-f596ff80-8107-11eb-9e12-426ad930b9f1.png)

- URL is the link for your post
- Caption is the post caption
- SourceUrl is the image posted

If you have an understanding of json, feel free to edit this as you see fit, more infomation can be found on this discord document section here: https://discord.com/developers/docs/resources/webhook.

Once compleated, select "Create Action", then click "Create".

## Step 5 - Test

From here you can now test to see if your applet is working correctly. Post a test image on your instagram page and wait until the applet pulls fron instagram. Alternatily you can click "Check Now" on the applet screen as below to check instantly for a new image: 

![image](https://user-images.githubusercontent.com/79415636/110522252-9d143200-8108-11eb-950e-31f29cf3d9c6.png)

Once the applet locates the image, It will push a notification to the selected channel on discord as shown below:

![image](https://user-images.githubusercontent.com/79415636/110522579-f3817080-8108-11eb-96f3-70210129398b.png)

- A black image has been used for testing
- "Test Caption" is the post Caption


Congratulations, Now any time you create an Instagram post, your discord commiunity will be notified!


### Referances

discord-ifttt.now.sh. (n.d.). discord-ifttt. [online] Available at: https://discord-ifttt.now.sh/ [Accessed 9 Mar. 2021]. 

Discord Developer Portal. (n.d.). Discord Developer Portal — API Docs for Bots and Developers. [online] Available at: https://discord.com/developers/docs/resources/webhook [Accessed 9 Mar. 2021].
