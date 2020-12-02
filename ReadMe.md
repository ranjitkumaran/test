# Sample Events Case Study with Firestore support
1. Getting started:  
Using Google Cloud Shell  
prerequisites: node and npm  
    these are available inside Google Cloud Shell.  
   1. open two separate terminal sessions:  
      * check that your Project Id is shown in yellow/gold in parentheses.
      * in one terminal **cd sample-master-firestore/internal**  
      * in the other terminal **cd sample-master-firestore/external**  
   1. run **npm install** in each terminal
   1. run **node server.js** in the *internal* terminal
   1. run **npm start** in the *external* terminal
   1. click on the "preview" button of your Cloud Shell.

1. The sample app  
Uses nodejs with the express web server on both server and client microservices.  
The internal service receives REST requests on port 8082 and returns data from a Google Firestore NoSQL collection.  
The external service unpacks json from the internal service into a html template in the Views folder
and returns it to the browser on port 8080.

1. Dependencies  
The internal and external both use the following npm packages:
   * Google Cloud - Firestore
     *  https://www.npmjs.com/package/@google-cloud/firestore  
   * express: a web server  
     * https://www.npmjs.com/package/express  
   * body-parser to convert json and form data in the request into parameters.  
     * https://www.npmjs.com/package/body-parser  
   * mocha, chai and supertest (for unit testing)  
     * https://www.npmjs.com/package/mocha  
     * https://www.npmjs.com/package/chai  
     * https://www.npmjs.com/package/supertest  
   * nyc for code coverage reporting  
     *  https://www.npmjs.com/package/nyc  
     
   The external service uses the following additional libraries:

   * express-handlebars ( a templating library)  
     * https://github.com/ericf/express-handlebars  
   * nock (for mocking the api call)  
     * https://www.npmjs.com/package/nock

