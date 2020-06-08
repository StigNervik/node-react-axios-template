## Node React Axios template

This project is a template project that can be used as a starter project if you want to create a node react with axios project.
Uses Node and React there the Node is written in TypeScript and React in JavaScript and axios to fetch / send messages to the server.

### How to build

Clone the project.
Go to the client directory and build the client.

```
$ yarn
$ yarn build
```

Go to the server project and build the server.

```
$ yarn
$ tsc
$ yarn start
```

### Build the server from scratch

Create project file and install TypeScript.

```
$ mkdir server
$ cd server
$ yarn init
$ yarn add typescript --dev

```

Update the package.json file to call typescript compilator from the command line:

```
"scripts": {
    "tsc": "tsc"
}
```

Create the typescript configuration file:

```
$ npx tsc --init
```

Install Express and Express types:

```
$ yarn add express @types/express
```

### Build the client

A React applicaton which is the frontend of this project.
React is a JavaScript library for building user interfaces.
Using Create React App that is the best way to start building a new single page application in React.

```
npx create-react-app client
cd client
yarn build
```

### Map backend to frontend

Create the server file, compile and run server:

```
$ touch server.ts
```

server.ts

```

import express = require('express');
import path = require('path');

const app: express.Application = express();

// Serve the static files from the React app
app.use(express.static(path.join(__dirname, '/../client/build')));

app.get('/test', (req, res) => {
  res.send('Node Express server running.');
});

// Handles any requests that don't match the ones above
app.get('*', (req, res) => {
  console.log('Current dir: ', __dirname);
  res.sendFile(path.join(__dirname + '/../client/build/index.html'));
});

const port = process.env.PORT || 5001;

app.listen(port, () => {
  console.log(`Server running on port ${port}`);
});

```

Compile and run the server:

```
$ tsc
$ yarn start
```

### Install Axios

Promise based HTTP client for the brrowser and node.js.

```
$ yarn add axios
```
