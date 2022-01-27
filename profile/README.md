![](https://user-images.githubusercontent.com/54647612/151277029-d661d85d-857d-4edc-a428-477149b5efe0.png)

lume is a software project to share a digital Olympic torch.

## How it works

At inception, the lume backend creates a root node. The admin creating the lume infrastructure can set this location freely. It then is necessary to create an info-screen at the set location to make the root node available to the users who have installed the lume app. Users then pass their flame to non-lit devices. Passing the flame is possible through NFC (exclusive to Android devices) or a QR code, spreading the fire all over the planet.

## Interaction of the components

![](https://user-images.githubusercontent.com/54647612/151425953-cb5d4242-6b29-4644-97d8-8855b9fcecc4.png)

The project consists of four main parts shown in the graph above.

The users' journey starts with the **Map**: They can explore how far the lume torch carriers have spread the lume network. This way, we intend to convince new users on downloading the app.

The app on a non-lit device interacts with a lit torch to receive the lume-fire onto the own device.
Such contact gets reported to the **REST-API** to collect and store the data in the **Neo4j Graph-Database**.

New and existing users can then explore the spread of the lume fire over time using the Map view.

[Read more...](../ProjectDetails.md)
