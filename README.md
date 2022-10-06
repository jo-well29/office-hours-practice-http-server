# office-hours-practice-http-server

## Practice Coding exercise: HTTP Server
---
We are going to make a sankofa server:

1. Initialize a node project, in the node-http-application folder. cd node-http-application and then run npm init.

2. Create an index.js file in this folder. Use the http library to create a hello world node application. The app should return the plain text of "Hello Sankofa" for each response, return a HTTP response code of 200 (success), and should run on port 8001. You should be able to start your server using the command npm start.

3. Add a couple more modules to the top of your index.js file to make the next steps easier.

```
const http = require('http')
const fs   = require('fs') //May not need this
const url = require('url');
```
4. Update your server function so that your application responds differently to different pathnames. If the path is /, the app should return a plain text response of "Hello Sankofa!". If the path is /instructors, the app should return a plain text response of "Hello Ana, Caston, and Jowel". For any other path, we should return a plain text message of "Sorry, that route does not exist."

5. Change the server function you wrote so that we also return the appropriate status code. The status codes of the application so that the / and instructor routes both return a 200 status, while the default option becomes a 404 response.

6. Create a function called renderReponse that takes in a string of text and an optional status code integer (if no status code is given, it should default to 200). This function should write the status code to the header and the response text to the response, then end the response. Refactor your server to take advantage of this new function.

7. Create a / path to account for query parameters. We should display some non-static content to the user. For example, fellow/?name=Richard should then response with the text Hello Richard!.

Finally, test your application. Make the following requests in your browser and see if your get the correct text.
```
http://localhost:8080/              => 'Hello Sankofa'
http://localhost:8080/instructors   => 'Hello Ana, Caston, and Jowel!'
http://localhost:8080/blah          => 'Sorry, that route does not exist.'
http://localhost:8080/fellows?name=Richard    => 'Hello Richard!'
http://localhost:8080/fellows?name=Celine     => 'Hello Celine!'
```





