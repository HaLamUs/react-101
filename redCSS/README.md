# 🔴 CSS

[⬅ Back](../README.md)

## Intro 
This project is my REACTION to this video ⬇️

<div>
  <a href="https://www.youtube.com/watch?v=bF5vEmiMzPg"><img src="https://img.youtube.com/vi/bF5vEmiMzPg/0.jpg" alt="IMAGE ALT TEXT"></a>
</div>

## Rule 
Problem: Prevent overlap styling. 
We apply Single responsibility principle 
We want our component to be responsible as little as possible
2 rules:
1. BEM naming convention 
2. CSS Module 

## Practice
### BEM Rule
### Item.js 
```js
function App() {
  return(
    <div>
    <h1>Hello World</h1>
    <Product name= "Google Home Max" description="Ur AI assistant" price={722.1}/>
    <Product name= "iPhone 12" description="The phone" price={22.1}/>
    <Product name= "Macbook pro" description="The laptop" price={7202.1}/>
    </div> 
  )
}
```

### Product.js 

```js
import from "./Product.css"
function Product() {
  return(
    <div className="product">
    # This outblock error not affect by product__error 
    <h2 className="error"> An error occured </h2>
    <Item />
    <h2 className="product__error"> An error occured </h2>
    <h3 className="product__price"> ${price} </h3>
    </div> 
  )
}
```
### Product.css 
```css
.product {
  padding: 20px;
  margin: 15px;
  border: 1px solid red;
}

/* BEM rules */
.product__error {
  color: blue;
  font-weight: bolder;
}
```
### CSS module 


### Product.js 
```js

import styles from "./Product.module.css"

function Product() {
  return(
    <div className={style.product}>
    # This outblock error not affect by product__error 
    <h2 className="error"> An error occured </h2>
    <Item />
    <h2 className= {style.error}> An error occured </h2>
    <h3 className="product__price"> ${price} </h3>
    </div> 
  )
}
```

### Product.module.css 
```css
.product {
  padding: 20px;
  margin: 15px;
  border: 1px solid red;
}

.error {
  color: blue;
  font-weight: bolder;
}
```


### CSS variables 
We still have the protection and the global var at the same time
### index.css 
```css
* {
  margin: 0;
  /* CSS variables*/
  --error-color: red;
}
```

### Product.module.css  
```css
.product {
  padding: 20px;
  margin: 15px;
  border: 1px solid red;
}

.error {
  color: var{--error-color};
  font-weight: bolder;
}
```


<p><img type="separator" height=8px width="100%" src="https://github.com/HaLamUs/nft-drop/blob/main/assets/aqua.png"></p>

## Author

This repo was developed by [@lamha](https://github.com/HaLamUs). 
Follow or connect with me on [my LinkedIn](https://www.linkedin.com/in/lamhacs). 

## License
