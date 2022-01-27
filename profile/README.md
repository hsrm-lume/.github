![](https://user-images.githubusercontent.com/54647612/151277029-d661d85d-857d-4edc-a428-477149b5efe0.png)

lume is a software project to share a digital Olympic torch.

## How it works

At inception, the lume backend creates a root node. The admin creating the lume infrastructure can set this location freely. It then is necessary to create an info-screen at the set location to make the root node available to the users who have installed the lume app. Users then pass their flame to non-lit devices. Passing the flame is possible through NFC (exclusive to Android devices) or a QR code, spreading the fire all over the planet.

## Interaction of the components

![](https://user-images.githubusercontent.com/54647612/151274861-ca9c4ee4-02a6-4e75-91f7-c55b29164160.png)

The project consists of four main parts shown in the graph above.

The users' journey starts with the **Map**: They can explore how far the lume torch carriers have spread the lume network. This way, we intend to convince new users on downloading the app.

The app on a non-lit device interacts with a lit torch to receive the lume-fire onto the own device.
Such contact gets reported to the **REST-API** to collect and store the data in the **Neo4j Graph-Database**.

New and existing users can then explore the spread of the lume fire over time using the Map view.

### Map

On the Map, users can explore the path of the lume fire, especially their one if viewing it via the app, inciting users to pass their flames to even more new users, enhancing their statistics.
A detailed breakdown and analysis of the data are made possible by the time slider to select a user-chosen point in time. Furthermore, opening the possibility to explore the path of lume fires between several nodes.
The Statistics provide further detailed and trackable number-based information.

### App
The app is a user-focused tool to share and enhance the extensive lume network. Available for iOS and Android, users can share the fire through NFC or Camera and QR-Code interaction. As well as sharing their fires, users can have a look at the map view. As well as having the same functionality as for everyone, personalised statistics are available to the user visiting through the app.

### REST-API

The REST-API serves as an interface between the neo4j database and reporting apps. It prevents directly writing to the database and conducts further server-sided validation.

### Neo4j

Neo4j is used to store the tree-like data structure because it offers excellent performance and easy querying even of more complex interrelationships.
