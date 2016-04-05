# React 學習筆記

## 1.Using React from npm
  * 兩種方法
    * 使用`browserify`
    * 使用`webpack`
  * ### 1.使用 **browserify**
    ```
    $ npm install --save react react-dom babelify babel-preset-react
    $ browserify -t [ babelify --presets [ react ] ] main.js -o bundle.js
    ```

  * ### 2.使用 **webpack**
    ```
    $ npm install --save react react-dom babel-preset-react
    $ webpack
    ```

  * code
    ```javascript
    // main.js
    var React = require('react');
    var ReactDOM = require('react-dom');

    ReactDOM.render(
      <h1>Hello, world!</h1>,
      document.getElementById('example')
    );
    ```

## 2.Quick Start Without npm
  * 先[下載](http://facebook.github.io/react/downloads.html)React
  * code
    ```html
    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="UTF-8" />
        <title>Hello React!</title>
        <script src="build/react.js"></script>
        <script src="build/react-dom.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.23/browser.min.js"></script>
      </head>
      <body>
        <div id="example"></div>
        <script type="text/babel">
          ReactDOM.render(
            <h1>Hello, world!</h1>,
            document.getElementById('example')
          );
        </script>
      </body>
    </html>
    ```
