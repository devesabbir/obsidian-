
## Needed packages for express-server

- `express` The web framework for Node.js that simplifies the creation of web applications
- `mongoose` MongoDB object modeling tool designed to work in an asynchronous environment
- `bcryptjs`bcryptjs is a JavaScript library that provides hashing functions based on the bcrypt hashing algorithm
- `nodemon` Monitors for changes and automatically restarts the server during development
- `morgan ` HTTP request logger middleware for Node.js
- `dotenv`  Loads environment variables from a `.env` file into `process.env`
- `body-parser `Middleware to parse incoming request bodies in a middleware before your handlers, available under `req.body`
- `http-errors ` `http-errors` module is a convenient way to create HTTP errors in your Express.js applications
- `xss-clean / express-sanitizer & express-rate-limit` Sanitize client request & set request limit
- `cors` Middleware for handling Cross-Origin Resource Sharing
- `helmet` Helps secure Express apps by setting various HTTP headers
- `cookie-parser` Middleware for parsing cookies attached to the client's request object
- `compression` Middleware to compress responses, improving performance
- `jsonwebtoken` package in Node.js, which is commonly used for working with JSON Web Tokens (JWT)

#Express-server #Backend #Packages_for_backend


#### Folder Structure (MVC)

```javascript 
// Folder Structure for redux react-redux

|-- node_modules
|-- public
|   |-- css
|   |-- js
|   |-- images
|-- src
|	|-- views
|	|-- routes
|	|   |-- index.js
|	|   |-- users.js
|	|-- controllers
|	|   |-- indexController.js
|	|   |-- userController.js
|	|-- models
|	|   |-- userModel.js
|	|-- config
|	|   |--config.js
|	|-- middlewares
|	|   |-- authentication.js
|	|-- utils
|	|   |-- helperFunctions.js
|	|-- tests
|	|   |-- testFile.js
|	|-- app.js
|-- server.js
|-- package.json
|-- package-lock.json

```


#project_structure #Express_Folder_Structure


#### Process 

###### MERN stack E-commerce project

  
1. Enviroment setup
2. Express server setup
3. API testing with Postman
4. Middleware & Types of Middleware
5. Express Error Handling Middleware → body-parser
6. How to handle HTTP errors → http-errors
7. How to secure API →→xss-clean, express-rate-limit
8. Environment variable & .gitignore 16 12. MVC Architecture
9. connect to MongoDB databse 18 14. Schema & Model for User
10. create seed route for testing
11. GET /api/users →isAdmin →getAllUsers → searchByNAME + pagination functionality
12. responseHandler controller for error or success
13. Get Single user by ID
14. delete single user by ID
15. delete image helper

  

## Packages

  

```shell

  #express #nodemon #morgan

```