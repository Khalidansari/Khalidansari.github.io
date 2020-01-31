---
layout: default
title: Licenses
---

# Salesforce Platform

Provide access to only Salesforce core functionality but not CRM like leads, opps, cases, etc. It does include Account, Contacts, etc.

## Salesforce

Provide full access to Salesforce features including the CRM

## Forc

There is no way for standard and custom components to talk to each other. There is one caveat to that and that is refreshView. This is a app level event fired when the view of a component is refreshed. This applies to both custom and standard views. This event can be caught in a custom component too. If there are some values which are changed in standard component then we can in a way tag its refresh to a custom component's refresh and vice versa.
