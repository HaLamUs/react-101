# useEffect

[⬅ Back](../README.md)

## Intro 
This project is my REACTION to this video ⬇️

<div>
  <a href="https://www.youtube.com/watch?v=UVhIMwHDS7k"><img src="https://img.youtube.com/vi/UVhIMwHDS7k/0.jpg" alt="IMAGE ALT TEXT"></a>
</div>

## What 
`useEffect` replaces life cycles functions in class component.

### ClassApp.js 
```js
export default class App extends Component {
  constructor(props) {
    this.state = {
      windowWidth: window.innerWdith,
    }
  }

  componentDidMount() {
    // Lifecycle func - when component mounts/loads
    console.log('The app component loaded')
  }

  componentDidUpdate(prevProps) {
    // Lifecycle func - when component props change 
  }

  componentWillUnmount() {
    // Lifecycle func - when component unmounts/cleanup func 
  }

  render() {
    return(
      <div>
        <h1> The UseEffect hook </h1>
      </div>
    )
  }

}
```

### App.js
```js

function App() {
  const [windowWidth, setWindowWidth] = useState(window.innerWidth);
  const [name, setName] = useState('')

  //On every render
  useEffect(()=> {
    window.addEventListener('resize', updateWindowWidth)
  })

  // on first Render/Mount only! - componentDidMount Alternative
  useEffect(()=> {

  }, [])

  // On first render + whenever dependency changes! - componentDidUpdate Alternative
  useEffect(()=>{
    console.log(`The name changed!: ${name}`);
    return() => {
      // cleanup...
      console.log(`We unmounted!`)
    }
  }, [name])

  // Follows the same rules, except this handles the unmounting on a component! - componentWillUnmount Alternative 
  useEffect(()=>{
    window.addEventListener('resize', updateWindowWidth)
    return() => {
      // when component unmounts, this cleanup code runs ...
      window.removeEventListener('resize', updateWindowWidth)
    }
  }, [])

  const updateWindowWidth = () => {
    setWindowWidth(window.innerWidth)
  }

  return (
    <div>
      <h1> The UseEffect hook </h1>
    </div>
  )
}

export default App;

``` 

## The end 
👍 I learned some

<p><img type="separator" height=8px width="100%" src="https://github.com/HaLamUs/nft-drop/blob/main/assets/aqua.png"></p>
## Author

This repo was developed by [@lamha](https://github.com/HaLamUs). 
Follow or connect with me on [my LinkedIn](https://www.linkedin.com/in/lamhacs). 

## License
