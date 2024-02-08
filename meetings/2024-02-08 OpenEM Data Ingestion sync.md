2024-02-08 OpenEM Dataingestion sync

Participants: Attila, Spencer, Andrzej, Philipp

### OpenEM Requirements Data ingestion (outside of ScopeM):
- is automatic ingestion a requirement?
	- No automatic ingestion of data into Scicat, only metadata extraction

### ScopeM Specific Requirements:
- GUI based manual Ingestions (web based)
	- Command line not an option
	- Automatic ingestion lower priority (at first)
	- Requirements on metadata
		- Only the minimal part for Scicat integration

### Metadata collection
- Automatic metadata extraction
- before data acquisition


### Workflows
#### 1. Minimal viable product: Metadata extraction and data upload triggered after session finished
After the data acquisition has finished, the user has to trigger the metadata extraction and data upload explicitly.

#### 2. Filling metadata before experiment and automatic ingestion after session has finished
The user can register their data and amend metadata before the session has started. After the session is finished the dataset is registered with SciCat and the data is uploaded automatically.

> **Decision**: Workflow 1. is the focused for the first implementation. Workflow 2. should build on the implementation of 1 and be kept in mind.

### Architecture:
Option 1: Direct data upload to PSI
The user upload the data directly from the facilities to PSI for ingestion. This applies to facilities that do not provide their own LTS.

Option 2: Local cache servers at facilities
The user upload the data to a cache server local to their facilities. That cache server then registers with and uploads the datasets to PSI with appropriate queuing and load balancing.

### Action Items:
- Attila: 	
	-	Architecture overview option 1 and option 2
	-	Initiate discussion within core-team
- All: Discuss pro and cons of options, decide
- Spencer: Distribute outcome to stakeholders, get feedback
- All: Decide on tech stack
