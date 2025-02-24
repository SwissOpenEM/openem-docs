# Admin Pages - Overview

### Participants
* Facilitiy
    * User
    * Facilitsy Manager
    * EM Data Server
    * Ingestor
    * Admin-Interface 

* PSI
    * SciCat Backend
    * SciCat Frontend
    * Data Cache
    * Keycloak IDP

* CSCS
    * LTS-Storage


### Groups for Access
* SciCat
    * Owner Group (Admin. Dataset)
    * Access Group 
    * Auth Roles
    * ...

* Ingestor
    * Admin
    * Read
    * Write

### Overview - Participants
```mermaid
flowchart LR
    subgraph Facility
        %% Entities
        direction TB
        user[User]
        faManager[Facility Manager]
        adminInterface[Admin Frontend]
        ingestor[Ingestor]
        emData[EM Data]

        %% Connections
        emData ---> ingestor 
        faManager --> adminInterface
        adminInterface --> ingestor
    end
    subgraph PSI
        %% Entities
        direction TB
        scicatbackend[SciCat Backend]
        scicatfrontend[SciCat Frontend]
        dataCache[Data Cache]
        keycloak[Keycloak IDP]

        %% Connections
        scicatfrontend --> scicatbackend
        scicatbackend --> keycloak
    end
    subgraph CSCS
        direction TB
        lts[LTS-Storage]
    end

    %% Connections (between subentities)

    user ---> scicatfrontend
    ingestor --> scicatbackend
    ingestor --> dataCache
    ingestor --> keycloak
    dataCache ----> lts
```