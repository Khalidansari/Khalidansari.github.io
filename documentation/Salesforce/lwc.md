---
layout: default
title: LWC
---

# Lightning Web Components

## Similarity to reactjs

1. Component based
2. Each component can have its own JS / template/ css file
3. Passing data using props from parent to child (child should expose the variable using @api)
4. Passing data using events from child to parent (similar to reactjs of passing the handler to child so that they can call)

## Properties specific to LWC due to its ties with Salesforce

1. To fetch the backend data or call a backend method, use @wire
2. LDS - provisions the data from backend. Helps in caching and making less server calls.
3. Use LMS to talk across application where child to parent and parent to child do not suffice

## Main parts of LWC - code wise

What is meant by reactive field? It means that if the value of that field changes then it will be updated across the component where it is used.

1. @track - annotate your variable while declaring it to tell lwc that this is a private reactive field. This annotation is no longer needed as Salesforce started doing that by default starting spring 2020.

2. @api -  annotate your variable while declaring it to tell lwc that this is a public reactive field. The only difference between @track and @api is that other components can see @api fields. This access is utilized for example in passing props from parent to child.

3. @wire - annotate your variable while declaring it to let lwc know that this reactive field needs to get its data from the backend. Salesforce uses LDS to make sure there are no unnecessary server calls if it can be fetched form cache.

4. Learn which all tags are available to make better use core features. For example <template if:true={somecondition}>

5. Passing data from parent to child is similar to reactjs (using props). Also, passing data from child to parent is kind of similar to reactjs where you pass the handler of the parent to child when embedding the child component in parent. One crucial thing to look out for is that if the event name in child is mytempchildevent then parent should try to use onmytempchildevent.
