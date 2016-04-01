```html
<!DOCTYPE html>
<html>
  <head>
    <script src="../build/react.js"></script>
    <script src="../build/react-dom.js"></script>
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

## 1.React Component 使用方法
  * 每個component都必須有自己的render方法
  * component開頭必須大寫
  * component只能有一個最外層的html label
    * `O <div><p></p></div>`
    * `X <div></div><p></p>`
  * 可以加入任意html屬性在Component，但須注意兩點
    * class需寫成className
    * for需寫成htmlFor
    * 因為class和for是js的保留字

  ```javascript
  var ComponentName = React.createClass({
    render: function() {
      return <h1>Hello {this.props.name}</h1>
    }
  });
  ReactDOM.render(
    <ComponentName name="deleav" />,
    document.getElementById("YEE");
  );
  ```

## 2.React this.props.children
  * this.props與component的html屬性互相對應
  * 例外 this.props.children 指的是component所有子節點
  * this.props.children 有三種 type
    1. undefined: 當前component沒有子節點
    2. object: 當前component有一個子節點P
    3. array: 當前component有多個子節點
  * React.Children method
    * 可使用 React.Children.map 來遍歷子節點

  ```javascript
  React.Children.map(this.props.children, function(child) {
    return <li>{child}</li>
  });
  ```
  
## PropTypes
  * component 的屬性可以是任意值，字串，函數等都可以。
  * 要驗證屬性的值可以用 PropTypes
  ```javascript
  var MyTitle = React.createClass({
  propTypes: {
    title: React.PropTypes.string.isRequired,
  },

  render: function() {
      return <h1> {this.props.title} </h1>;
    }
  });
  ```
  * 這裡的意思是`MyTitle`這個component的`title`屬性必須是string並且是required
