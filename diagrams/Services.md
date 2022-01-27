# Service Deployment diagram

![](http://www.plantuml.com/plantuml/png/PP3FJW8n48VlVOeD9pqCGUEH4118y612b1lXC6o7fTe_JRUB6kExEqEZOVMocTb-N_kRcROPK-wSLQfzDJvYGbSjw82TpHjwppDh6k_8vwhc3wKBQerQ6zzKDxTA7VW7LOEncMYADdnKTN0nj3IeFjMvz7B5uhxQgl5-ii2CUsn9CUyftBsedRh0Pkk7mZqjdpV0dN2sSmI9sWmOJPz_n5XuBWH5ttGM4pYCS4Y1OtlznzXdOwdzjM0ZhRZio562bjA94cjVlMWn5eaBmHDXdS5ZDYU2sXgGcFstLlDbKLQ1myynQLYwph8I_ByhZlNPvaM13c_-QWGoNQ-NVSZ4mydF6DAMSv20Ia925qVN1PPsc4nppAnm6YNxXVEFxT5eJNvNNb5gIbvtpdu3)

<!--
@startuml

skinparam DefaultTextAlignment center
skinparam Padding 12

frame "<i>deploy compose" {
component DB [
<b>Database
<i>neo4j
]

component API [
<b>REST-API
<i>lume-rest-api
]

component Map [
<b>Map
<i>angular-map-frontend
]

component Mbtiles [
<b>Map-Tiles
<i>maptiler-server
]
}

component App [
<b>App
<i>react-native-cli-lume
]

component HCE [
<b>Host-Card-Emulation
<i>react-native-hce
]

DB -down(0- Map
DB -down(0- API
Map .> Mbtiles
Map -down- App
App -up0)- API
App .right.> HCE
API -right[hidden]- Map


@enduml
-->
