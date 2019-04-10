
## Problem
We are currently pursuing the bootcamp, april 2019 cohort, the second week challenge: Address-book. When trying to setup the project, and specifically the Webpack config (which is a module bundler) for running the Cucumber feature tests - we get an error when we are running `$ yarn run build` in our terminal

### How did you try to solve the problem?
We installed the babel dependencies to the project by running the following command in our terminal:

```
$ yarn add webpack webpack-cli babel-loader babel-preset-es2015 babel-polyfill babel-register --dev
```

We then created the webpack.config.js file, and added the following code to the file (as the instructions states):

````
module.exports = {
  entry: "./src/app.js",
  output: {
    filename: "bundle.js",
    path: `${__dirname}/dist`
  },

  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: "babel-loader",
          options: {
            presets: ["es2015"]
          }
        }
      }
    ]
  }
};
````
When trying to run `$ yarn run build` in our terminal, we encounter an error message saying that we have the wrong babel-loader version - and it cannot be found in the installed Node Modules... (unfortunately we did not save any screenshots before uploading this issue..)
