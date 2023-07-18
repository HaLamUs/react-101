# componentType

[⬅ Back](../README.md)

## Intro 
This project is my REACTION to this video ⬇️

<div>
  <a href="https://www.youtube.com/watch?v=yc6elaGOoGQ"><img src="https://img.youtube.com/vi/yc6elaGOoGQ/0.jpg" alt="IMAGE ALT TEXT"></a>
</div>

## Comparison
### 'Class component' 🆚  'Function component' 
Previous ONLY class based components could have STATE 
Now with React HOOKS function components can 

### React fundatmentals
- STATE
- PROPS

`props` is what you pass into the component 
`state` is local vars 

### Example 
#### Function

```js
function App(props) {
  const [name, setName] = useState(``)

  return (
    <div>
      <h1> My name is {name} </h1>
      <h1> I am {props.sex} </h1>
    </div>
  )
}

export default App;
```

#### Class
```js
export default class AppClass extends Component {
  constructor(props) {
    super[props]
    this.state = {
      name: ""
    }
  }

  render() {
    return (
      <div>
        <h1> My name is {this.state.name} </h1>
        <h1> I am {this.props.sex} </h1>
    </div>
    )
  }
}
```


<p><img type="separator" height=8px width="100%" src="https://github.com/HaLamUs/nft-drop/blob/main/assets/aqua.png"></p>

## Author

This repo was developed by [@lamha](https://github.com/HaLamUs). 
Follow or connect with me on [my LinkedIn](https://www.linkedin.com/in/lamhacs). 

## License
