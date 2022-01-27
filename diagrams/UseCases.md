# UseCases for lume app

![](http://www.plantuml.com/plantuml/png/jPBDgi8m48NtynH3zmfQTI5I19_11mZfQ8FvAPa9t4lfkz-ajuletgvEvpldJ6boPL5HahDWwI4e0QDv3eAzYQJ510zAIuZOsEG8xqonGSMOE48nAF-qj48rZWrEW1cILfp7J8Gvh8SbSx_jQcYNFJNUrtXKp6-q_Mnsl_ySWqUdnjLs-BInA34iHZE6HmdLfSVQBL7frrkj35HLds06I1nni-dAvrQwhVIkqeTA7m7o0BVRydB2CpRJvMAyjgcdhfkRWbjSwBvG_EQJLzEFaE-NpJu8hGSVF5hZNt0BlZVb0fodn1JNVs8u6sR8EImPk6QLdFq3)

<!--
@startuml
left to right direction
actor "lume User" as usr
rectangle "lume app" {
  usecase "see torch" as UC1
  usecase "light torch" as UC2
  usecase "pass torch" as UC3
  usecase "see my torch on map" as UC4
  usecase "see statistics of my torch" as UC5
  usecase "track my torch on the map" as UC6
}

usr -[plain]-> UC2
usr -[plain]-> UC3
usr -[plain]-> UC1
usr -[plain]-> UC4
usr -[plain]-> UC5

UC4 ..> UC6 : "{<<include>>}"

UC3 .> UC2 : "                                                                                             {<<extend>>}"
note right on link
Condition:{user torch is on}
end note
@enduml
-->
