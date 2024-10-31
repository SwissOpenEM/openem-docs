# Ingestion Sequence

### Participants
* Scicat Backend (Service)
* Ingestor UI (Web-Frontend)
* Ingestor Backend (Service)
* Metadata Extractor (Executable)

### Endpoints ###
* See API-speficiation

### Data
* Extractor-Information: (Defines Method, Extractor, Schema per Extractor)
* userMetadata: Metadata which is entered manually by the user
* extractorMetadata: Metadata which is automatically extracted by the Metadata Extractor
* mergedMetadata: Combined Metadata of userMetadata and extractorMetadata
* Dataset: filePath of the Dataset

### Ingestion-Flow

```mermaid
sequenceDiagram
  participant S as Scicat Backend
  participant U as Ingestor UI 
  participant B as Ingestor Backend 
  participant M as Metadata Extractor
    B ->> B: On service startup: Initialize, validate and install extractors 
    S -->> U: Serve Ingestor UI
    activate U
    U ->> B: Establish Connection: GET /version
    deactivate U
    activate B
    B -->> U: return version
    deactivate B
    activate U
    U ->> B: Get Available Extractors, Methods and Schemas: GET /extractor
    deactivate U
    activate B
    B -->> U: return [] extractorName, method, schema
    deactivate B
    activate U
    U ->> U: User selects Method
    U ->> B: Get Folder List: GET /dataset
    deactivate U
    activate B
    B -->> U: return folders
    deactivate B

    activate U
    U ->> B: Extract extractorMetadata: POST /extractor {filePath, extractorName}
    deactivate U
    activate B
    B -->> M: Invoke Extractor
    activate M
    B -->> U: return extractionJobId
    activate U
    U ->> U: User enters userMetadata and confirm
    M ->> M: write metadata via stdout
    M -->> B: return status code
    deactivate M
    deactivate B
    deactivate U

    loop Wait for Automatic Metadata Extraction
        activate U
        U ->> B: Ask for state: GET /extractor {extractionJobId}
        deactivate U
        activate B
        B ->> B: Read extraction status file
        B -->> U: return {progress (int 0-100), metadata if 100}
        deactivate B
        activate U
        
        alt Extraction complete
            U ->> U: break
        else Extraction incomplete
            U ->> U: Update progress-bar and continue
        end
        deactivate U
    end

    activate U
    U ->> U: User checks and edit extractorMetadata
    U ->> B: Merge metadata: POST /metadata {userMetadata, extractorMetadata}
    deactivate U
    activate B
    B -->> U: return mergedMetadata
    deactivate B
    activate U
    U ->> U: Display mergedMetadata and confirm
    deactivate U
    U ->> B: Start ingestion: POST /transfer {mergedMetadata}
    activate B
    B -->> U: return ingestionId
    deactivate B
    
```
