## Interaction of the components

![](https://user-images.githubusercontent.com/54647612/151425953-cb5d4242-6b29-4644-97d8-8855b9fcecc4.png)

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

## Diagrams

For more details on program flows etc. see the following Diagramms:

- [Use Cases](../diagrams/UseCases.md)
- [Services interrelationships](../diagrams/Services.md)
- [State Machine for the App](../diagrams/AppStateMachine.md)
- [Sequence Diagramm for lighting a new device](../diagrams/MainSequenceDiagram.md)
- [Sequence Diagramm for ErrorHandling](../diagrams/SequenceDiagramErrorHandling.md)
