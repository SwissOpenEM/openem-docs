# Ingestion Sequence

### Participants

-   Scicat Backend (Service)
-   Ingestor UI (Web-Frontend)
-   Ingestor Backend (Service)
-   Metadata Extractor (Executable)

### Endpoints

-   See API-speficiation

### Data

-   Extractor-Information: (Defines Method, Extractor, Schema per Extractor)
-   userMetadata: Metadata which is entered manually by the user
-   extractorMetadata: Metadata which is automatically extracted by the Metadata Extractor
-   mergedMetadata: Combined Metadata of userMetadata and extractorMetadata
-   Dataset: filePath of the Dataset

### Ingestion-Flow

```mermaid
sequenceDiagram
  participant S as Scicat Backend
  participant U as Ingestor UI
  participant B as Ingestor Backend
  participant M as Metadata Extractor
    B ->> B: On service startup: Initialize, validate and install extractors (config.yml)
    S -->> U: Serve Ingestor UI
    activate U
    U ->> B: Establish Connection: GET /version
    deactivate U
    activate B
    B -->> U: return version
    deactivate B

    activate U
    U ->> B: Check for logged in user: GET /userinfo
    deactivate U
    activate B
    B -->> U: return info / error
    deactivate B

    activate U
    U ->> B: Login if necessary: POST /login
    deactivate U
    activate B
    B -->> U: return Cookie
    deactivate B

    activate U
    U ->> B: Do health check: GET /health
    deactivate U
    activate B
    B -->> U: return health status
    deactivate B
    activate U
    U ->> B: Get Available Extractors, Methods and Schemas(? -> verify): GET /extractor
    deactivate U
    activate B
    B -->> U: return [] extractorName, method, schema (? -> verify)
    deactivate B
    activate U
    U ->> U: User selects Method
    U ->> B: Get Folder List: GET /dataset
    deactivate U
    activate B
    B -->> U: return datasets
    deactivate B

    activate U
    U -->> B: Extract extractorMetadata: GET /metadata Param{filePath, extractorName} // SSE 
    activate B
    B -->> M: Invoke Extractor
    activate M
    U ->> U: User enters userMetadata and confirm
    B -->> U: return status
    M -->> B: Send progress via stdout / stderr
    B -->> U: Send update via subscription
    M ->> M: write metadata to file
    M -->> B: return status code
    deactivate M
    U ->> U: Wait for final metadata result
    B -->> U: return metadata
    deactivate B
    deactivate U

    activate U
    U ->> U: User checks and edit extractorMetadata
    U ->> U: Merge metadata
    U ->> U: Display mergedMetadata and confirm
    U ->> B: Start ingestion: POST /dataset
    deactivate U
    activate B
    B -->> U: return transferId
    deactivate B

```
