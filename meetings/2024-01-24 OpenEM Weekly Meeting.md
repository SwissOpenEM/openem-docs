---
created: 2024-01-24
tags: [meeting, openem]
---
# Agenda

## Onboarding Status

| Name | github |
| ---- | ---- |
| Spencer Bliven | sbliven |
| Despina Adamopoulou | despadam |
| Yves Tittes | ytittes |
| Philipp Wissmann | phwissmann |
| Attila Nacsa | consolethinks |
| Matt Baker |  |


| Name | Slack | Taiga | PSI account | openem list | swissplus list | Github | Meeting Invite | Google Drive | Scicat slack | Scicat email |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| Spencer | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Despina | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Philipp | ✅ |  | ✅ | ✅ |  |  | ✅ |  | ~ | ~ |
| Yves | ✅ |  | ✅ | ✅ | ~ |  | ✅ |  |  |  |
| Attila | ✅ |  | ✅ | ✅ |  |  | ✅ |  | ✅ | ✅ |
| Sofya |  |  |  |  |  |  |  |  |  |  |
| Andy |  |  |  |  |✅  |  |  |  |  |  |
| Matt Baker | ✅ |  | ✅ | ✅ |  |  | ✅ |  |  |  |
| Andrzej Rzepiela | ✅ |  | ✅ | ✅ |  |  | ✅ |  |  |  |
| Daniel Böhringer | ✅ |  | ✅ | ✅ |  |  |  |  |  |  |
## Organizational
- New repo for notes & docs: [openem-docs](https://github.com/SwissOpenEM/openem-docs) (private)
    - Could be replaced by confluence
- Meeting organization
    - Suggestion to have daily/regular standup meetings (15 minutes to review status)
    - 9:30-9:45 Mon, Tues, Thurs, Fri?
    - Attendance is optional. I will likely miss some too.
- Kanban choice
    - Taiga vs Github project

## Status Updates

### Spencer
- Productive visit to UNIGE 2024-01-23
- Job release
    - [scicat-backend-next#1021](https://github.com/SciCatProject/scicat-backend-next/pull/1021) ready to merge with auth configuration fields and compilation fixes
    - Plan to refactor somewhat after compilation works
- Workshops
    - SwissPlus Workshop announced. Waiting for our secretary to get back to help with the registration page
    - Should this be sponsored by OpenEM or have a registration fee?
- Confluence status
    - 20 Licenses for OpenEM were approved
    - PSI is discussing the exact location for external projects like ours
    - External accounts are being tested. SSO works, but invitation to spaces seem not to

### Despina

- Job controller compiling!
  - Issue with ENOENT error
- Scheduled meeting with PREMISE (Giovanni Pizzi ORD project) for EM standards (battery application)
  - Invite Yves

### Yves

- Information on metadata required by Engel group for ET
- Script for extracting metadata from SerialEM. Updating other script for Thermo-Fischer (EPU)
- Meeting Bern about TF instruments

### Attila

- Doing test ingestion with SciCat
  - pyscicat docs need updating
  - Schema error: validate against https://scicatproject.github.io/SciCatEditor/
- How to associate files with SciCat owners
  - Does any facility have a User Managment System?
    - Yves: Basel splits commercial/academic
    - Spencer: None at PSI
    - Andy: Open to User Managment Service
    - Need to communicate this to facility managers since it has potential user impact
  - Possible implementations
    - Website where users can mark datasets as ready for ingestion
    - Beamline managers are responsible for marking data as ready

### Philipp

- Met ScopeM
  - Web interface (user management overlap)
- Evaluating intermediate storage technologies
- 

# Action Items
- [ ] Describe PSI cluster access & ingestion
