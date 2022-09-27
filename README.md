### Set up

Make a basic node package, and initialize a git repository:

```
mkdir express-intro
cd express-intro
npm init
git init .
```

Add the following line to `package.json`'s `scripts` entry:

```json
"start": "node index.js"
```

You will now be able to see the result of executing `index.js` using the `npm run start` command:

```
➜  express-intro git:(main) npm run start

> express-intro@1.0.0 start
> node index.js

Hi
```

To be able to use ES6 syntax, add the following line to your `package.json` file:

```json
"type": "module"
```

### Add Dependencies

We will be installing project dependencies that will be placed in a folder named `node_modules` in our project. In order to avoid committing this folder to github, we want to tell git to ignore the folder:

```
echo "node_modules/" >> .gitignore
```

To add a dependency to your project, use the `npm install` command:

```
npm install express
```

Note that this updates your `package.json` file to include `express`.

Update `index.js` to create an express app:

```js
import express from "express";

const app = express();
const port = 3000;

app.get("/", (_request, response) => {
  response.send("Hello World!");
});

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`);
});
```

Save and run `npm run start` (there's a shorthand specifically for the `start` script that allows you to use `npm start`):

```
➜  express-intro git:(main) ✗ npm start

> express-intro@1.0.0 start
> node index.js

Example app listening on port 3000
```

In your browser, got to [http://localhost:3000](http://localhost:3000) to see the result.
