# Use Cases
This documents lists various use-cases and aspects pertaining to them.

```plantuml
@startuml
skinparam actorStyle awesome

:New User: as :Newb:
:Newb: ..> :User: : becomes
:User: ..> :Developer: : becomes
:Newb: .right.> (Tutorial)
:Newb: -down-> (Simulation)
:User: -> (Simulation)
:Developer: -> (Debugging)
    
(Tutorial) -> (Simulation)

(Debugging) -> (Logging)

@enduml
```

# 1. First-time User

## 1.1. Tasks

# 2. Advanced User

## 2.1. Tasks



# 3. Developer

## 3.1. Needs

...

## 3.x.1. JADE implementations

## 3.x.2. Extensions

## 3.x.3. Plug-ins