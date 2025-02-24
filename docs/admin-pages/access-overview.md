# Admin Pages - Overview

### Participants
* Facilitiy
    * User
    * EM Data Server
    * Ingestor

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
        ingestor[Ingestor]

        %% Connections
        emData[EM Data] --> ingestor 
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

### Overview - Admin Interface
```mermaid
flowchart LR
    subgraph Admin-Interface[SciCat Frontend?]
        %% Entities
        direction TB
        admin[Admin-Interface]
    end
    subgraph Facility
        %% Entities
        direction TB
        ingestor[Ingestor]

        %% Connections
    end
    subgraph PSI
        direction TB
        scicatbackend[SciCat Backend]
        keycloak[Keycloak IDP]
    end

    %% Connections (between subentities)
    admin --> scicatbackend
    admin --> ingestor
    admin --> keycloak
```