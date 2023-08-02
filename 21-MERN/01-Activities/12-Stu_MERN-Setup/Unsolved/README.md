# Add Comments to Implementation of the MERN-stack Architecture

## Root-level Functionality

* TODO: Explain what each script does in the root-level `package.json` file:

```json
"scripts": {
  "start": "node server/server.js",
  // start starts the serving using server.js
  "develop": "concurrently \"cd server && npm run watch\" \"cd client && npm start\"",
  // This script is used for development purposes.
  "install": "cd server && npm i && cd ../client && npm i",
  // This script is used to install dependencies for both the server and client applications.
  "seed": "cd server && npm run seed",
  // This script is used to seed or populate the database with initial data.
  "build": "cd client && npm run build"
  // This script is used to build the client-side application for production.
},
```

## Client-side Functionality

* TODO: Explain what this script does in the client-side `client/package.json` file:

```json
"proxy": "http://localhost:3001",
// It is used to set up a proxy for API requests during development.
```

## Server-side Functionality
* TODO: Add a comment describing the functionality of this block of code in `server/server.js`:

```js
if (process.env.NODE_ENV === 'production') {
  app.use(express.static(path.join(__dirname, '../client/build')));
}
// The code block is responsible for serving the client-side application's static files when the server is running in a production environment.
```

* TODO: Add a comment describing the functionality of this route in `server/server.js`:

```js
app.get('*', (req, res) => {
  res.sendFile(path.join(__dirname, '../client/build/index.html'));
});
// This route is a catch-all route that is used when the server receives a GET request for any undefined route or route that hasn't been explicitly handled by other routes in the server. It ensures that the client-side application's main HTML file is sent back to the client regardless of the requested URL.
```
