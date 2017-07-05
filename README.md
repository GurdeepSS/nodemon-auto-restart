# nodemon-auto-restart

Manually restarting Node.js application is a tiring and tedious job. [Nodemon]() is the best solution available to autorestart a nodejs app server in development mode.

## Step 1
Organize the source directory `src` and initiate it with an `app.js` or `index.js` or `server.js` or any other convention you use to bootstrap a Node.js server.

Update the `package.json` file accordingly by adding a `start` script.

```json
{
  "name": "nodemon-auto-restart",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "start": "node src/index.js"
  },
  "keywords": [],
  "author": "Aman Mittal <amandeepmittal@live.com> (http://amandeepmittal.github.io/)",
  "license": "MIT"
}
```

## Step 2
Add `express` or any other framework as dependency to bootstrap a minimal server.

Code for a minimal server:

```javascript
'use strict';

const express = require('express');
const app = express();

app.use('/', (req, res) => {
  res.status(200).send('Hello World!');
});

app.listen(3000);
```

In first terminal window start the server:

```shell
$ npm run start
> node src/index.js
```

In second terminal window, request the url to test if the api is working and to see the response message:

```shell
$ curl -X GET http://localhost:3000/
Hello World!
```

Now if I change the response message, I have to restart the server to get the desired result:

```javascript
app.use('/', (req, res) => {
  res.status(200).send('Lorem Ipsum');
});
```

Use `Command + C` in mac or `Ctrl + C` in windows to stop the currently running server and restart it by using the same command before: `npm run start`.

Using the curl command again from terminal window we get the desired result:

```shell
curl -X GET http://localhost:3000/
Lorem Ipsum
```

This whole process is repetitive will slow your development of any package or application. Better solution is to use `nodemon`.

## Step 3
Add nodemon as `devDependency`:

```shell
$ npm i -D nodemon
```