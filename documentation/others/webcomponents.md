---
layout: default
---
# Web Components

## History

## Basics

1. JS - Extends HTMLCustomElement + reference Template + attach to shadow dom
2. HTML - Define template
3. CSS - Define css for the custom Component
4. Use - import the above in the HTML and then use <component name> to use the component like native tags.

## Lightning Web Components (Salesforce)

'message' is identified (binded) in the below example:

1. JS -

        import { LightningElement } from 'lwc';
        export default class App extends LightningElement {
            message = 'Hello World';
        }

2. HTML - define Template

        <template>
            <input value={message}></input>
        </template>

3. CSS - If needed

kebab case not allowed in Salesforce for naming files but you can use camel case and Salesforce converts it to kebab case which can then be referenced in other places.

4. configuration - js-meta.xml
