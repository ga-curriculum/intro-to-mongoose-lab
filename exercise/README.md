# ![Intro to Mongoose Lab - Exercise](./assets/hero.png)

# Terminal CRM

## Description

A **Customer Relationship Management** (CRM) tool is an application that allows a company to keep track of their customers.  In this lab. you're going to create a terminal-based CRM application that will have full CRUD functionality on a single model: Customer.  The model will have the following fields:

- name: String
- age: Number

The user will start your application by running the following command in the terminal:

```zsh
node app.js
```

**NOTE:** the `prompt-sync` package, used to get user input in the terminal, acts oddly with `nodemon`, so it's best to use `node app.js` to start the app and then manually do `^c` and then `node app.js` again when you've made changes to code that you want to test.

Remember to set up a `.gitignore` file as well as a `.env` file so that you can safely store the value for MONGODB_URI locally, without it being pushed up to GitHub.

## Suggestions

- When figuring out what the user wants to do, it's probably easiest to prompt them to choose from various options in a numbered list.  This way, the user just enters a number and the application knows what to do next.
- When dealing with choosing a specific customer to update or delete, it's probably easiest to list the customers in the database along with their ids.  Then prompt the user to copy and paste the id of the user that needs to be updated/deleted.  Below is one possible example:

```
Welcome to the CRM

What would you like to do?

  1. Create a customer
  2. View all customers
  3. Update a customer
  4. Delete a customer
  5. quit

Number of action to run: 3

Below is a list of customers: 

id: 658226acdcbecfe9b99d5421 --  Name: Matt. Age: 43
id: 65825d1ead6cd90c5c430e24 --  Name: Vivienne. Age: 6

Copy and paste the id of the customer you would like to update here: 658226acdcbecfe9b99d5421

What is the customer's new name? Bilbo
What is the customer's new age? 50

What would you like to do?

  1. Create a customer
  2. View all customers
  3. Update a customer
  4. Delete a customer
  5. quit

Number of action to run: 2

id: 658226acdcbecfe9b99d5421 --  Name: Bilbo. Age: 50
id: 65825d1ead6cd90c5c430e24 --  Name: Vivienne. Age: 6

What would you like to do?

  1. Create a customer
  2. View all customers
  3. Update a customer
  4. Delete a customer
  5. quit

Number of action to run: 5

exiting...
```

## Hint

Once you run `node app.js`, the application will not exit until the connection to MongoDB is also closed.  To close the connection to MongoDB, put the following code in an appropriate place:

```javascript
mongoose.connection.close()
```