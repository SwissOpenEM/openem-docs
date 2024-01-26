---
tags: 
created: 2024-01-26
---
# General Info

- PSI currently uses the v3 backend
- There are production, QA, and dev environments. Please don't use production for test data.
# Access to API

1. Go to https://discovery-qa.psi.ch
2. Log on using your PSI account
3. Go to settings. Copy your 'SciCat Token'
4. Go to https://dacat-qa.psi.ch/explorer/
5. Paste token in the top authentication field
6. Test v3 API through swagger

The procedure is identical for production (remove `-qa` from URLs).