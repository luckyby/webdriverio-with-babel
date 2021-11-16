# webdriverio 'import' mode with babel

Checking out how to use webdriverio 'import' mode with Babel. 


It's described in Babe's docs:
https://v6.webdriver.io/docs/babel.html

To do so, first install the necessary Babel dependencies:

```javascript
npm install --save-dev @babel/core @babel/cli @babel/preset-env @babel/register
```

Make sure your ```babel.config.js``` is configured properly.

The simplest setup you can use is:
```javascript
//babel.config.js
module.exports = {
  presets: [
    ['@babel/preset-env', {
      targets: {
        node: "current"
      }
    }]
  ]
}
```

There are multiple ways to setup Babel using the WDIO testrunner depending on the test framework you are using for Mocha:

```javascript
// wdio.conf.js
exports.config = {
    // ...
    mochaOpts: {
        ui: 'bdd',
        require: ['@babel/register']
    },
    // ...
}
```




<br>
Now possible to run test file example.e2e.js in 'import' mode by: <br>
<strong>npx wdio run ./wdio.conf.js --spec example.e2e.js</strong>


