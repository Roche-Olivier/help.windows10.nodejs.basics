[![Index](https://github.com/Roche-Olivier/help.windows10.nodejs.basics/blob/master/_content/_images/footer.png "Table fo contents")](https://github.com/Roche-Olivier/help.windows10.nodejs.basics)
## Initialize your project
**Where do we start with such a mountain of data available to us.**

> Create a readme

ALWAYS create a `README.md` file in your application root folder , so that the next developer knows what the application is about and how it works.

> Initialize your project

Then we always need to initialize a node project.

> Create a git ignore file

Be sure to create a git ignore file to that all the binaries does not get checked in , only the source.

**Starting the initialization**

Create a new folder for your project (project root folder).

Open a command prompt window and navigate to your project root folder.

Type in the following command:

`> npm init`

This will open a prompt for you to add all your relevant details of the application.


You will be prompted on the command line to confirm your input , type "yes"
```
{
  "name": "myapp",
  "version": "1.0.0",
  "description": "my app description",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "your name",
  "license": "ISC"
}


Is this ok? (yes) yes
```
This will initialize your project and create a `package.json` file

Your `package.json` file will look like this now:
```
{
  "name": "myapp",
  "version": "1.0.0",
  "description": "my app description",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "your name",
  "license": "ISC"
}
```

Add an `index.js` file to your project root folder,and then add the following code the the `index.js` file:
```
console.log("hello world")
```

The only thing left to do is add a start command to the  `package.json` file like this:
```
{
  "name": "myapp",
  "version": "1.0.0",
  "description": "my app description",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    _"start": "node index.js"_
  },
  "author": "your name",
  "license": "ISC"
}

```

You can now type the command:
 
`> npm start`

on the command line in your project root folder.


This will show 'hello world' on the output and then end the application.

You now have a working node application.


[![Index](https://github.com/Roche-Olivier/help.windows10.nodejs.basics/blob/master/_content/_images/footer.png "Table fo contents")](https://github.com/Roche-Olivier/help.windows10.nodejs.basics)