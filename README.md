# AutoBinding-in-React 

#### Method 1 - Not using ES6 classes

```js
var Button = React.createClass({
  handler:function(e){
   ....
  },
  render:function(){
    return (
      <button onClick={this.handler} >
        Click me
      </button>
    );
  }
})
```

#### Method 2 - Using ES5 bind 
```js
class Button extends React.Component{
    handler(){
     ...
    }
    render(){
       return (
          <button onClick={this.handler.bind(this)} >
            Click me
          </button>
       );
    }

}
```

#### Method 3 - Binding in constructor  
```js
class Button extends React.Component{
    constructor(){
    this.handler = this.handler.bind(this) 
    }
    handler(){
     ...
    }
    render(){
       return (
          <button onClick={this.handler} >
            Click me
          </button>
       );
    }

}
```
#### Method 4 - Fat arrows  
```js
class Button extends React.Component{
    handler = ()=>{
     ...
    }
    render(){
       return (
          <button onClick={this.handler} >
            Click me
          </button>
       );
    }

}
```

#### Method 5 - ES7 Bind syntax  in constructor
```js
class Button extends React.Component{
    constructor(){
    this.handler = ::this.handler;
    }
    handler(){
     ...
    }
    render(){
       return (
          <button onClick={this.handler} >
            Click me
          </button>
       );
    }

}
```
#### Method 6 - ES7 Bind syntax inline
```js
class Button extends React.Component{
    handler(){
     ...
    }
    render(){
       return (
          <button onClick={::this.handler} >
            Click me
          </button>
       );
    }

}
```
