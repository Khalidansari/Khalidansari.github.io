---
layout: default
title: About
---

# Salesforce Tips

1. Indexing on formula field is possible now if the formula is deterministic. If not then do consider the fact that any SOQL filtering on that field will not work if its indeterministic. In such a case it is better to put the logic in a before update/insert trigger.

2. Data in recycle bin is still recalculated for sharing rules. So you might not want to keep the data too long in recycle bin.

## Black Tab Access

Populating created date and created by during insert - Need to do it from setup. No need to create case with Salesforce.
The history table of that object will still keep the created by and created date as the actual date and user who did it. So you can
pull report on the records you inserted based on history table.

 
