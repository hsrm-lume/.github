# Sequence Diagram for lighting a torch

![](http://www.plantuml.com/plantuml/png/XL71SjGm3BtdApIvjCnqRvpsmBHGED4UW4wFZ3PM4p69xRMLNJuVMKbsqZ3GGs9RUfBUUxhDWad6eQ-4fIUelpuzVDx1TpgEv1k2UyOsuL1NKM7SS4GlKD_52Cyi7NmSasVVme-Gcgu6pD2p_9Jogh3H4-e7P0zFcPAbHxsiUwtoe5qDWp6-XdoZBBkxo7EMAuU21ynAzv72-rzmFxyDu4keAeDWzw4qsuE9p8KHdr389bo8Nb0QWI2TratngBV7Bvz0LHmJDC5HfRW9pliPHB-R3drBmFubf065WyzmVPYDcK3iRaovNPGytK0CcGlstPeLL_hfW4d37XArdEL2g0bU50tNwWvviMvDnxtxVz_94Fl3Rc6VnuPoVXdxUKWovfMZJPaHMXowqggbR15-1OD6i2MjtKY9fTA4wxmkdBDPR5fUxoT4yXa6Z71YEYykFzF1iYt99GTdbWxOEpwn6x4lgrrlTggffcFbfC40lRDEnv4IK_wtHSleHAABtAmw_-tICcyHz0PTHrl2-cszEbjcZItFM_9k7Fe_)

<!--
@startuml
title "LUME- Sequence Diagram"
participant "App With Burning Torch" as lit_torch
actor "Main User" as user
participant "Main User App" as app
participant "Rest-Api" as api
database "Neo4j Database" as neo4j
user -> app: starts
activate app
lit_torch -> app: lit other torch per NFC or qr code
app -> api: torch exchange informations (burning torch id, user id, date, position)
activate api
api -> neo4j: register torch contact (parent id, child id, date, position)
activate neo4j
neo4j -[plain]-> api: sucessful registration
deactivate neo4j
api -[plain]-> app: 'successful exchange' message
deactivate api
app -[plain]-> user: shows lit torch
user -> app: opens map view
app -> Webapp: get map view with individual stats
activate Webapp
Webapp -> neo4j: stats and map queries
activate neo4j
neo4j -[plain]-> Webapp: return torch exchanges
deactivate neo4j
Webapp -[plain]-> app: map view with individual stats
deactivate Webapp
app-[plain]-> user: shows webapp
deactivate app
@enduml
-->
