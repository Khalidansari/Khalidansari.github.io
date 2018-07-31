---
layout: page
title: About
---

# Salesforce Tips

1. Indexing on formula field is possible now if the formula is deterministic. If not then do consider the fact that any SOQL filtering on that field will not work if its indeterministic. In such a case it is better to put the logic in a before update/insert trigger.

2. Data in recycle bin is still recalculated for sharing rules. So you might not want to keep the data too long in recycle bin.

3.
