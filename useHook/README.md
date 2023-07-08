# useHook

[⬅ Back](../README.md)


## Intro 
This project is my REACTION to this video ⬇️

<div>
  <a href="https://www.youtube.com/watch?v=nshyjApIovo"><img src="https://img.youtube.com/vi/nshyjApIovo/0.jpg" alt="IMAGE ALT TEXT"></a>
</div>

## What
Custom Hooks: Sharing logic between components 

## useEffect version 
### App.js 
```js
function App() {
  const [joke, setJoke] = useState('')

  useEffect(()=> {
    const fetchJoke = async () => 
      await fetch(`http://api.icndb.com/jokes?random>firstName=Lam&lastName=Ha`)
      .then((res) => res.json())
      .then((data) => {
        setJoke(data.value.joke)
      })
    fetchJoke();
  }, [])

  return (
    <div>
      <h1> The Joje generator </h1>
      <h2> {joke} </h2>
      <button> Generate Joke </button>
    </div>
  )
}
```

## custom hook version 
### Ver 1
### useRandomJoke.js
```js
function useRandomJoke(firstName, lastName) {
  const [joke, setJoke] = useState('')

  useEffect(()=> {
    const fetchJoke = async () => 
      await fetch(`http://api.icndb.com/jokes?random>firstName={firstName}&lastName={lastName}`)
      .then((res) => res.json())
      .then((data) => {
        setJoke(data.value.joke)
      })
    fetchJoke();
  }, [firstName, lastName]) // ☢️ <-- Remember add these vars otherwise got unexpected behaviors

  return joke
}
```
### App.js 
```js
function App() {
  const joke = useRandomJoke('Lam', 'Ha')

  return (
    <div>
      <h1> The Joje generator </h1>
      <h2> {joke} </h2>
      <button> Generate Joke </button>
    </div>
  )
}
```
### Ver 2
This will hit api every single typing 
### App.js 
```js
function App() {
  const joke = useRandomJoke('Lam', 'Ha')
  const [firstName, setFirstName] = useState(``)
  const [lastName, setLastName] = useState(``)

  const generateJoke = (e) => {
    e.preventDefault();
  }

  return (
    <div>
      <h1> The Joje generator </h1>
      <h2> {joke} </h2>
      <form>
        <input placeholder='first name' value={firstName} onChange={(e) => setFirstName(e.target.value)}/>
        <input placeholder='last name' value={lastName} onChange={(e) => setLastName(e.target.value)}/>
        <button onClick={generateJoke}> Generate Joke </button>
      </form>
      
    </div>
  )
}
```



### Ver 3
`useRef` as a pointer to value which need to be tracked 

### App.js 
```js
function App() {
  const joke = useRandomJoke('Lam', 'Ha')
  const [firstName, setFirstName] = useState(``)
  const [lastName, setLastName] = useState(``)
  const firstNameRef = useRef(null)
  const lastNameRef = useRef(null)

  const generateJoke = (e) => {
    e.preventDefault();
  }

  return (
    <div>
      <h1> The Joje generator </h1>
      <h2> {joke} </h2>
      <form>
        <input placeholder='first name' ref={firstNameRef}/>
        <input placeholder='last name' ref={lastNameRef}/>
        <button onClick={generateJoke}> Generate Joke </button>
      </form>
      
    </div>
  )
}
```

<p><img type="separator" height=8px width="100%" src="https://github.com/HaLamUs/nft-drop/blob/main/assets/aqua.png"></p>
## Author

This repo was developed by [@lamha](https://github.com/HaLamUs). 
Follow or connect with me on [my LinkedIn](https://www.linkedin.com/in/lamhacs). 

## License
