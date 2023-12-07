
## Needed packages for express-server

- `express` (The web framework for Node.js that simplifies the creation of web applications)
- `mongoose` (MongoDB object modeling tool designed to work in an asynchronous environment)
- `bcryptjs`(bcryptjs is a JavaScript library that provides hashing functions based on the bcrypt hashing algorithm)
- `nodemon` (Monitors for changes and automatically restarts the server during development) 
- `morgan ` (HTTP request logger middleware for Node.js)
- `dotenv`  (Loads environment variables from a `.env` file into `process.env`)
- `body-parser `(Middleware to parse incoming request bodies in a middleware before your handlers, available under `req.body`)
- `http-errors ` (`http-errors` module is a convenient way to create HTTP errors in your Express.js applications)
- `xss-clean / express-sanitizer & express-rate-limit` (Sanitize client request & set request limit)
- `cors` (Middleware for handling Cross-Origin Resource Sharing)
- `helmet` (Helps secure Express apps by setting various HTTP headers)
- `cookie-parser` (Middleware for parsing cookies attached to the client's request object)
- `compression` (Middleware to compress responses, improving performance)


#Express-server #Backend #Packages_for_backend


#### Folder Structure (MVC)

```javascript 
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