---
created: 2024-02-01
tags:
  - meeting
  - openem
---
Slack updates
# Minutes

## Attila
- Started working on an automatic SciCat dataset creation tool in python
- Learning and testing Scitacean as an alternative to PySciCat
- Ask for updates on SciCat documentation (the entire API part is missing, I don't know for example what "Size" means in RawDataset, it's never described what units it uses)
    - Spencer: [Swagger docs](https://dacat-qa.psi.ch/explorer/](https://dacat-qa.psi.ch/explorer/). Size in bytes
## Despina
- Had a first discussion with [@Yves Tittes](https://openem.slack.com/team/U06B4UPTJQZ) to see what our data and metadata look like. He shared a list of fields he has extracted and I will try to find out how many we have in common
- Starting today to work again on [https://github.com/orgs/SwissOpenEM/projects/2?pane=issue&itemId=51488740](https://github.com/orgs/SwissOpenEM/projects/2?pane=issue&itemId=51488740)
## Philipp
I got a prototype of a web based data upload running; it's a multipart upload to Minio with checksums for each part. Its upload speed is limited by the checksums so I need to see how well this works on the real system. It's web based because a UI is needed and I don't want to deploy an executable. But I'll quickly compare it with a python implementation of the same thing. Maybe this is interesting for you, [@Spencer](https://openem.slack.com/team/U04R5ME9DFH) [@Attila Nacsa](https://openem.slack.com/team/U06EKG68LHW)
## Spencer
- 10 registrations so far, 7 from CH
- Working on mid-term review for swissuniversities. Please keep track of your expenses and in-kind contributions carefully so future reviews  are easier
## Yves
(Site visit to UNIBE)

