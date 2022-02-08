1. Cypress commands: Cypress comes with set of commands to interact with the webpage.
They can be of following types: parent,child and dual commands
Cypress also provides an API for creating custom commands which we can define in support folder/index.js

A)PARENT COMMANDS: these commands begin a new chain of Cypress commands.
Like: cy.get() , cy.visit(), cy.request() etc.

B) CHILD COMMANDS: these commands are chained to a parent command or another child command Eg: .click() .type() .find() etc 

C) DUAL COMMANDS: these commands acts such that they can either start a chain or be chained to an existing one. Eg: .contains() , .screenshot() , .wait() etc.


Assertions: Cypress provides assertions from various frameworks like Chai, Sinon, JQuery etc.

Retry-ability in Cypress: Hepls cypress to effectively test dynamic apps which have asynchrous tasks.
Cypress commands are smart such that they wait for app to update while running a test untill the timeout is met And, if an asserion following a DOM Query fails, cypress also give a functionlity to retry the test.
however cypress doesnt retry every command tho, it only retris those commands which query the DOM.


Alias: dont create state changing alias in the before each hook. like click,dblclick etc




//Cypress eosystem and tools
Stub Responses. , non stubbed responses
1. Test defines responses which arent the actual sever respones and can be controlled (like status, body, header,delay etc) perfect for JSON, dont provide coverage for sever endpoints but are fast asf.
2. Directlt hit server and wait for response (Recommended for SSR) Slower, save the DB from scratch

For implementing 1 we need followin commands:
a) cy.server() : used to start server to begin routing and to change the behaviour of your network request
b) cy.route() : used to manage the behaviour of the n/w request and you can also pass the response with it.
c) cy.request() : direct to http server not stubbed
