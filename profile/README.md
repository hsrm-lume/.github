![](https://user-images.githubusercontent.com/54647612/151277029-d661d85d-857d-4edc-a428-477149b5efe0.png)

lume is a software project to share a digital olympic torch.

## How it works

Users can pass on their flame to non-lit devices. This can happen through NFC (which is exclusive to android devices) or a QR code.
This way, the fire can spread

## Interaction of the components

![](https://user-images.githubusercontent.com/54647612/151274861-ca9c4ee4-02a6-4e75-91f7-c55b29164160.png)

The project consists of four main parts shown in the graph above.

User journey starts with the **Map**: Here the User can explore how big the lume network is so far and gets hooked on downloading the app.

The **App** can then be used to interact with a device with a lit torch to obtain the lume-fire onto the own device.
Such contact then gets reported to the **REST-API** to collect the data and store it in the **Neo4j Graph-Database**.

New and existing users can then explore the pread of the lume fire over time using the Map view.

### Map

On the Map users can explore the path of the lume fire, and especially their own one if viewing it via the app.
This incites users to pass their flames to even more new users to improve their own statistics.
A detailed breakdown and analysis of the data is made possible by the time slider to select a wayback point in time and the possibility to explore the path of lume fires between several nodes.
The Statistics provide further detailed and trackable number-based information.

### App

The key part of the project is the lume app. ...

### REST-API

The REST-API serves as an interface between the neo4j database and reporting apps. This prevents publishing of write credentials to the database and opens up possibility for further server-sided validation.

### Neo4j

Neo4j is used to store the tree-like datastructure because it offers great performance and easy querying even of more complex interrelationships.
