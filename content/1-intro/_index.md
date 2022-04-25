+++
title = "Intro"
weight = 1
+++

## Prerequisites

Before we start going through the workshop, make sure that you have **VSCode** or **VSCodium** installed on your machine.
For the convenience, we will reference the IDE as **VSCode** going forward.
> If you are familiar with Git, you can clone following GitHub Repository and open it with VSCode:
> https://github.com/camel-k-integration-workshop/camel-k-workshop

We need to install the VSCode extensions -- **Extension Pack for Apache Camel by Red Hat** for later use.
{{< figure src="../images/extension_pack.png?width=50pc&classes=border,shadow" title="Click image to enlarge" >}}

### Telegram Account, Bot and Chat ID

> Note: if you haven't used telegram before, you can simply download the `Telegram` mobile app and create a new account there.  
Alternatively, you can follow [this link](https://telegram.org/) to get the desktop version. 

#### Create a telegram bot
&#9744; Search for username ***@BotFather*** \
&#9744; Start the chat: ***/start*** \
&#9744; Send message: ***/newbot***  to ***@BotFather*** \
&#9744; Follow the instructions of ***@BotFather*** and create name and username for the bot. \
&#9744; Once the bot is created, you will receive a token to access the HTTP API, **keep the token secure and store it safely**. 

{{< figure src="../images/botfather2.png?width=25pc&classes=border,shadow" title="Click image to enlarge" >}}

&#9744; Now search for your newly-created bot and click ***/start*** to initiate the conversation with the bot. Feel free to say "Hi"!


{{% notice tip %}}
If you encounter any issues during the process or you seek additional information about bots, official Telegram website provides complete instructions on [how to create a bot with the help of BotFather.](https://core.telegram.org/bots#6-botfather) 
{{% /notice %}}

#### Get our Chat ID
&#9744; Search for username ***@RawDataBot*** with name `Telegram Bot Raw` \
&#9744; Start the chat: ***/start*** \
&#9744; You will receive a message from the ***@RawDataBot***, store the value of `"id"` in the `"chat"` section somewhere safe. 

{{% notice warning %}}
Once we get the telegram bot token and the chat ID, remember to save them somewhere safe and easily accessible. We will need them in the following examples.
{{% /notice %}}