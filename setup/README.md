# ![Intro to Mongoose Lab - Setup](./assets/hero.png)

## Initialization 

Open your Terminal application and navigate to your **`~/code/ga/labs`** directory:

```bash
cd ~/code/ga/labs
```

Make a new directory called **`intro-to-mongoose-lab`**, then enter this directory and initialize the project:

```bash
mkdir intro-to-mongoose-lab
cd intro-to-mongoose-lab
touch app.js
npm init -y
```

With the initialization completed, open the contents of the directory in VS Code:

```bash
code .
```

Define all of your code in a `app.js` file.

## Install `prompt-sync`

Prompt-sync is a package that allows us to easily get input from the user in the terminal.  Install it with:

```zsh
npm i prompt-sync
```

Copy the following code and paste it into your `app.js` to get an example of `prompt-sync` working:

```js
const prompt = require('prompt-sync')();
const username = prompt('What is your name? ');
console.log(`Your name is ${username}`);
```