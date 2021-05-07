# Rollback

## Two phase rollback for distributed systems

> Source - https://aws.amazon.com/builders-library/ensuring-rollback-safety-during-deployments/

Take following example to understand the issue with single phase deployment. Change: Servers will read and write in JSON instead of XML. If few servers are deployed the new version while others are still getting deployed. In such a case services might start failing as few servers will write in JSON but other servers can't still read it.

Two phase:

1. Phase 1 - prepare phase - can read in both JSON and XML but write in XML
2. Phase 2 - activate phase - can read in both JSON and XML but write in JSON.

Caution:

1. You can either rollback Phase 1 to original or Phase 2 to Phase 1 but can't move back to orignal version after activate phase as the data would already be written in JSON. So better to keep a brake period after prepare phase and if everything looks good then rollback.
2. Removing the functionality to read XML can't be taken out until a backend process updates the data type in DB from XML to JSON. This is called backfilling.
