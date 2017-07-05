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
    "start": "src/index.js"
  },
  "keywords": [],
  "author": "Aman Mittal <amandeepmittal@live.com> (http://amandeepmittal.github.io/)",
  "license": "MIT"
}
```