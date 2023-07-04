# Redux

[⬅ Back](../README.md)

## Intro 
This project is my REACTION to this video ⬇️

<div>
  <a href="https://www.youtube.com/watch?v=ss-_S1Vyxa0"><img src="https://img.youtube.com/vi/ss-_S1Vyxa0/0.jpg" alt="IMAGE ALT TEXT"></a>
</div>

## Before 
It's the last option you don't need it

Typically, we choose Redux for global state management if we work on a larger, complex project. 

## Get in
### store.ts
```js
import { configureStore } from '@reduxjs/toolkit'
import counterReducer from './slices/counterSlice'

export const store = configureStore({
  reducer: {
    counter: counterReducer
  },
})

export type RootState = ReturnType<typeof store.getState>
export type AppDispatch = typeof store.distpatch

```

## app.ts 
```js
import { store } from "../store";
import { Provider } from "react-redux"

function MyApp({Component, pageProps}: AppProps) {
  return(
    <Provider store={store}>
      <Component {...pageProps} />
    </Provider>
  );
}

export default MyApp;

```

## counterSlice.ts 
🔴 This file will contain all of counter information but at global data layer

```js
export interface CounterState {
  value: number
}

const initialState: CounterState = {
  value: 0
}

export const counterSlice = createSlice({
  name: 'counter',
  initialState,
  reducers: { // just action
    increment: (state) => {
      state.value += 1; 
    },
    decrement: (state) => {
      state.value -= 1;
    }
  }
})

export const { increment, decrement } = counterSlice.actions;
export const selectValue = (state: RootState) => state.counter.value;
export default counterSlice.reducer

```

## index.tsx
```js

import { useSelector, useDispatch } from 'react-redux'
import { decrement, increment, selectValue } from '../slices/counterSlice'
import type { RootState } from '../store'

const Home: NextPage = () => {
  // const count = useSelector((state: RootState) => state.counter.value)
  const count = useSelector(selectValue)
  const dispatch = useDispatch();

  return (
    <div>
      <h1> The value of count is { count } </h1>
      <button onClick = { dispatch.decrement() }> decrement </button> 
      <button onClick = { dispatch.increment() }> increment </button> 
    </div>
  )
}
```

## Note 
install Redux extension maybe helpful 


---
## Author

This repo was developed by [@lamha](https://github.com/HaLamUs). 
Follow or connect with me on [my LinkedIn](https://www.linkedin.com/in/lamhacs). 

## License
