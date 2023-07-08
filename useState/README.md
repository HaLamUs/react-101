# useState

[⬅ Back](../README.md)

## Intro 
This project is my REACTION to this video ⬇️

<div>
  <a href="https://www.youtube.com/watch?v=kkuq0gTGRFQ"><img src="https://img.youtube.com/vi/kkuq0gTGRFQ/0.jpg" alt="IMAGE ALT TEXT"></a>
</div>

## What 
`useState` is local memory for component 
For able to re-render we need follow the React way that update the state (local mem) of the component 
Compare the new value using something called virtual dom against the actual value that is on the screen. So React will know which part of web page to go ahead and refresh it

**Note**: Refresh page the state will reset 

### Not re-render version 
```js
function Ap() {
  let count = 0

  const increment = () => {
    count += 1
  }

  const decrement = () => {
    count -= 1
  }

  return (
    <div>
      <h1> This count is: {count} </h1>
      <button onClick={increment}> + </button>
      <button onClick={decrement}> - </button>
    </div>
  )
}

```

### useState version 
```js
function Ap() {
  const [count, setCount] = useState(0)

  const increment = () => {
    setCount(count + 1)
  }

  const decrement = () => {
    setCount(count - 1)
  }

  return (
    <div>
      <h1> This count is: {count} </h1>
      <button onClick={increment}> + </button>
      <button onClick={decrement}> - </button>
    </div>
  )
}

```

### AppClass.js 
This is async version. Which means it could be out-sync 
```js
export default AppClass extends Components {
  constructor(props) {
    super(props)

    this.state = {
      count: 0
    }
  }

  increment = () => {
    this.setState({
      count: this.state.count + 1
    })
  }

  decrement = () => {
    this.setState({
      count: this.state.count - 1
    })
  }

  render() {
    return (
      <div>
        <h1> This count is: {this.state.count} </h1>
        <button onClick={this.increment}> + </button>
        <button onClick={this.decrement}> - </button>
      </div>
    )
  }
}
```

### AppClass.js 
Constraint state, make sure latest 
```js
export default AppClass extends Components {
  constructor(props) {
    super(props)

    this.state = {
      count: 0
    }
  }

  increment = () => {
    this.setState((previousState) => ({
      count: previousState.count + 1
    }))
  }

  decrement = () => {(
    this.setState((previousState) => {
      count: previousState.count - 1
    }))
  }

  render() {
    return (
      <div>
        <h1> This count is: {this.state.count} </h1>
        <button onClick={this.increment}> + </button>
        <button onClick={this.decrement}> - </button>
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
