# ![Intro to Mongoose Lab - Exercise](./assets/hero.png)

## Terminal CRM

### Objective

A **Customer Relationship Management** (CRM) tool is an application that allows a company to keep track of their customers. In this lab. you're going to create a terminal-based CRM application that will have full CRUD functionality on a single model: Customer.

## Dependencies

### Install `prompt-sync`

Prompt-sync is a package that allows us to easily collect input from a user in the terminal. This is how we will interact with our application.

Install the package:

```bash
npm i prompt-sync
```

To ensure prompt-sync is working, add the following code to `app.js` and test it using node:

```js
const prompt = require('prompt-sync')();

const username = prompt('What is your name? ');

console.log(`Your name is ${username}`);
```

You will also need the following packages to complete this lab:

- mongoose
- dotenv

## Define the model

1. Create a new model file and build the customer schema.

2. The customer model will have the following fields:

   - name: String
   - age: Number

## Make the database connection

Initialize Mongoose and MongoDB Connection:

1. Set up Mongoose in your application.
2. Ensure you have a `.env` file for your MongoDB URI and a `.gitignore` file to avoid pushing sensitive data to GitHub.

## Developing the user interface

- Start by displaying a welcome message to the user
- Implement a simple menu system that lets the user choose an action (Create, View, Update, Delete, Quit). Use prompt-sync to get the user's choice and handle it accordingly.
- When figuring out what the user wants to do, it's probably easiest to prompt them to choose from various options in a numbered list.  This way, the user just enters a number and the application knows what to do next.
- When dealing with choosing a specific customer to update or delete, it's probably easiest to list the customers in the database along with their ids.  Then prompt the user to enter id of the user that needs to be updated/deleted.

## Starting the application

Start your application by running the following command in the terminal:

```bash
node app.js
```

**NOTE**:
The prompt-sync package, used for user input in the terminal, may not work well with nodemon. To test changes, stop the app using `Ctrl+C` and restart it with `node app.js`.

## Sample exchange

Use the following example as a guide when designing your application:

### Starting the application

```bash
Welcome to the CRM

What would you like to do?

  1. Create a customer
  2. View all customers
  3. Update a customer
  4. Delete a customer
  5. quit

Number of action to run: 
# user inputs 3
```

### Updating a customer

```bash
Below is a list of customers: 

id: 658226acdcbecfe9b99d5421 --  Name: Matt, Age: 43
id: 65825d1ead6cd90c5c430e24 --  Name: Vivienne, Age: 6

Copy and paste the id of the customer you would like to update here: 
# user inputs 658226acdcbecfe9b99d5421

What is the customers new name?
# user inputs Bilbo
What is the customers new age?
# user inputs 50
```

### Choosing next action

```bash
What would you like to do?

  1. Create a customer
  2. View all customers
  3. Update a customer
  4. Delete a customer
  5. Quit

Number of action to run: 
# user inputs 2
```

### Viewing updated customers

```bash
id: 658226acdcbecfe9b99d5421 --  Name: Bilbo, Age: 50
id: 65825d1ead6cd90c5c430e24 --  Name: Vivienne, Age: 6
```

### Choosing next action

```bash
What would you like to do?

  1. Create a customer
  2. View all customers
  3. Update a customer
  4. Delete a customer
  5. Quit

Number of action to run: 
# user inputs 5
```

Exiting the Application

```bash
exiting...
```

## Exiting the application

When you run your CRM application using `node app.js`, it starts an active session. For the application to exit cleanly, it is essential to close the MongoDB connection. This prevents potential issues like memory leaks or hanging processes.

When the exit condition is met (e.g., the user selects 'Quit'), call `mongoose.connection.close()` in `app.js`. This command safely closes the connection to your MongoDB database.
