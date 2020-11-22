---
layout: default
---
# Old way - Using ANT

No matter which OS you are using, these commands will come handy to any developer interested in quick scanning of code. For those are on Windows system can install cygwin to get a command prompt where they can execute the following commands.

> Using ant to retrieve results from a previously executed task. Replace REQUESTED_ID with actual id e.g. 0Af800000006OKL

```sh
ant rp -Dsf.asyncRequestId=REQUESTED_ID
```

# New way - Using SFDX

There were maintainability issues in the "old way" as there were certain metadata which were one large file rather than more granular, for example, object metadata had fields, validation rules, list views, etc. To resolve this, Salesforce introduced sfdx, which serves a lot more than just this. Using sfdx you can convert that big metadata file into more granular parts and maintain that in codebase and during deployment time it combines those back into one big file.

 > Convert granular codebase to old format and put it in output folder

 sfdx force:source:convert -r ./force-app/main/default/ -d ../output

 > Deploy the old format to env1 environment

 sfdx force:mdapi:deploy -d mdapioutput/ -u env1 -w 100

 
