+++
title = "Task 2 - Using Kamelets"
weight = 8
+++

[This example](https://github.com/camel-k-integration-workshop/camel-k-workshop/tree/main/02-kamelets-examples) demonstrates how to create a simple Chuck Norris Kamelet source and how to integrate it with Telegram. Our goal is to connect to a website containing Chuck Norris jokes via API, get a joke every few seconds and print it in the terminal first, and then also send it to our Telegram channel.

{{< figure src="../images/camelk_workshop01_arch.png?width=50pc&classes=border,shadow" title="Click image to enlarge" >}}

> If you still don't have your Telegram account, bot or chat ID, please refer to the first chapter "Intro" for the instructions on how to get them. 


#### What are Kamelets 

Kamelets are pieces of code that allow users to connect to external systems via simplified interface. All the details about the integration are hidden inside the kamelet, and users use it by writing just one line of code in the integration file. 

As kamelets look like any other Camel component, experienced developers will enjoy using them as much, and will quickly browse through all the already available, predefined Catalog Kamelets. It is of course possible to create your own kamelets too!
You can define your own library of reusable kamelets for your organisation. And desirebly, contribute them to the Camel community.

Camel provides more than 300 components out of the box, therefore we can create a Kamelet in a simple way, making use of one of the components already available. Most of the Kamelets available in the official catalog, are simple ones having only a remapping of the Kamelet properties into Camel endpoint parameters.

Kamelets have two kinds of connectors, **sources** and **sinks**. Sources produce the data and sinks consume the data and optionally produce a response. 


#### Let's get started

&#9744; `oc new-project kamelet-example` - create a new project for the second example \
&#9744; `kamel init chuck-norris-source.kamelet.yaml` - initiate a simple Kamelet template \

> You can also use `kamel init xxxx-source.kamelet.yaml / xxxx-sink.kamelet.yaml` to instantiate a kamelet template for creating your own custom kamelet of a given type. 

&#9744; Modify your kamelet, or copy the entire kamelet code from: [chuck-norris-source.kamelet.yaml](https://github.com/camel-k-integration-workshop/camel-k-workshop/blob/main/02-kamelets-examples/chuck-norris-source.kamelet.yaml) \ 
&#9744; `oc apply -f chuck-norris-source.kamelet.yaml` - use `kamel` CLI to create the chuck norris source kamelet on your OpenShift instance \
&#9744; `oc get kamelets` - check if the chuck norris source is ready \
&#9744; create a [chuck-norris-example.groovy](https://github.com/camel-k-integration-workshop/camel-k-workshop/blob/main/02-kamelets-examples/chuck-norris-example.groovy) \
&#9744; `kamel run chuck-norris-example.groovy --dev`- run the integration using chuck norris kamelet in the "dev" mode 

> You should see the jokes appearing in the terminal. 

> Groovy is just one of many programming languages, that you can use to write integration files. All the supported languages for Camel K integration can be found [here.](https://camel.apache.org/camel-k/1.8.x/languages/languages.html)

&#9744; Change the `.to('log:info')` to `.to("telegram:bots?authorizationToken=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX&chatID=XXXXXXXXXXXXX")`  - simply comment the line number 2 and uncomment the line number 3. 
&#9744; Provide the bot Authorization Token and chat ID in places marked by `X` characters.
&#9744; Save the file. After saving, your integration will reload automatically, because we are running it in "dev" mode.
> Your Telegram bot should now be sending you Chuck Norris jokes!

&#9744; `oc delete project chuck-norris` - clean up the project
