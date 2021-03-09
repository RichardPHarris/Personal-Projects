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
![image](https://user-images.githubusercontent.com/79415636/110516736-e3b25e00-8101-11eb-822c-4467eecf2bb3.png)


On the left of the screen you will see a list of server setting catagorys, please chose 
