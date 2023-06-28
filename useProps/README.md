# useProps

[⬅ Back](../README.md)

## Intro 
This project is my REACTION to this video ⬇️

<div>
  <a href="https://www.youtube.com/watch?v=kHJSNFU7H4U"><img src="https://img.youtube.com/vi/kHJSNFU7H4U/0.jpg" alt="IMAGE ALT TEXT"></a>
</div>

## What 
- `props` aka properties. The way you pass pieces of informations to React components, to make the components customize 
- `props` is pass from top-down (parent-to-child)
- `props` is read-only. `useState` if it's the case.

## Code 
- `App.js`
```js
function App(){
  return(
    <div>
      <h1> Hello </h1>
      <Product name="Google Home" description="Your AI assistant" price={19.99}>
      <Product name="Google Home 2" description="Your AI assistant" price={19.99}>
      <Product name="Google Home 3" description="Your AI assistant" price={19.99}>
    </div>
  )
}
```

- `Product.js`
```js
function Product(props) {
  return (
    <div>
      <h1> {props.name} </h1>
      <h2> {props.description} </h2>
      <h3> $ {props.price} </h3>
      <ItemDescription name={props.name} description={props.description}>
    </div>
  )
}
```

- `ItemDescription.js`
```js
function ItemDescription({name, description}) {
  return (
    <div>
      <h1> {name} </h1>
      <h2> {description} </h2>
    </div>
  )
}
```

- Class `ItemDescription.js`
```js
export default class ItemDescription extends Component {
  render(){
    return(
      <div>
      <h1> {this.props.name} </h1>
      <h2> {this.props.description} </h2>
    </div>
    )
  }
}
```

---
## Author

This repo was developed by [@lamha](https://github.com/HaLamUs). 
Follow or connect with me on [my LinkedIn](https://www.linkedin.com/in/lamhacs). 

## License
