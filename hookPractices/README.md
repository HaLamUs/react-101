# hookPractices

[⬅ Back](../README.md)

## Intro 
This project is my REACTION to this video ⬇️

<div>
  <a href="https://www.youtube.com/watch?v=NZEUDJvpQMM"><img src="https://img.youtube.com/vi/NZEUDJvpQMM/0.jpg" alt="IMAGE ALT TEXT"></a>
</div>


## Guidelines 
Rule of Hooks 
1. Only call hooks (useState or useEffect) at the TOP lvl 
- This means dont call hooks inside loops, CONDITIONS (if/else) or nested functions
- Always use Hooks at the top lvl of ur react function 
- By following this rule, u ensure hooks are called in the same order each time a component renders 
- This allows react to correctly preserve the state of the hooks b/w useState/useEffect calls 

2. Dont call hooks from regular JS functions 
- Call hooks from React FC's 
- Call hooks from custom hooks 

## Example 
```js
function App() {
  const [input, setInput] = useState('') // 1
  const [todos, setTodos] = useState([]) // 2
  const [randomNo, setRandomNo] = useState(Math.floor(Math.random() * 101)) // 3

  // ❌ BAD - break the call order 
  if (randomNo > 50) {
    const [tets, setTest] = useState('Whoops') // 4
  }

  // ✅
  const [tets, setTest] = useState('Whoops') // 4

  // ❌ BAD - conditional must go inside the useEffect 
  if (randomNo < 50) {
    useEffect(()=> { // 5 we may skip the #5, in that case the CALL ORDER will break 
      console.log('render')
    })
  }

  // ✅
  useEffect(()=> { // 5
    if (randomNo > 50) {
      console.log('render')
    }
  })

  // ❌ BAD - no nested functions 
  const testing = () => {
    useEffect(()=> { // 6  
      console.log('render');
    })
  }

  // ✅
  useEffect(()=> { // 6
    const testing = () => {
      console.log('render');
    }
    testing()
  })

  // ✅
  useEffect(()=> { // 7 
    console.log('render')
  })
}



```

## IN SHORT 
Using `linter` you'll safe

<p><img type="separator" height=8px width="100%" src="https://github.com/HaLamUs/nft-drop/blob/main/assets/aqua.png"></p>

## Author

This repo was developed by [@lamha](https://github.com/HaLamUs). 
Follow or connect with me on [my LinkedIn](https://www.linkedin.com/in/lamhacs). 

## License
