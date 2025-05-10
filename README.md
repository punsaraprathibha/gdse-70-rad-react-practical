# 🚀 React Counter App (Class Components)
Getting some hands-on experience about React Life Cycle, State and Props Management, using Class components.

Let's install `React generator` or `React Buddy` as a plugin to our IDE to easily create React components.

1. Firstly let's clean up the current `App.tsx` file content our project.
2. Let's define `App.tsx` fie's structure as a React class component like this.
 ```typescript jsx
import React, {Component} from 'react';
import './App.css';

class App extends Component {
    render() {
        return (
            <div className="app">
                <h1>This is App Component!</h1>
            </div>
        );
    }
}

export default App;
```
In `App.css`:
```css
.app {
  background-color: blue;
}
```

3. Here we're going to create a counter app. So, we need to create a new package called `counter` and a new component called `Counter.tsx` inside it.
```typescript jsx
import React, {Component} from 'react';
import './Counter.css';

class Counter extends Component {
    render() {
        return (
            <div className="counter">
                <h1>This is Counter App Component!</h1>
            </div>
        );
    }
}

export default Counter;
```
In `Counter.css`
```css
.counter {
  background-color: red;
}
```

Define `Counter` inside the div in `App.tsx` in order to render it in the browser:
```typescript jsx
render() {
    return (
        <div className="App">
            <Counter/>
        </div>
    );
}
```

4. Now let's design the content of the counter app inside render function.
```typescript jsx
render() {
    return (
        <div className="container">
            <h1>React Counter (Class Component)</h1>
            <h2>Count: 0</h2>
            <div>
                <button className="button">+</button>
                <button className="button">-</button>
            </div>
        </div>
    );
```

In `Counter.css`
```css
.container {
    text-align: center;
    padding: 2rem;
    font-family: Arial, serif;
    border: 2px solid #0e0e0e;
    border-radius: 10px;
    width: 300px;
    margin: 2rem auto;
    background-color: #d9d5d5;
}

.button {
    font-size: 1.5rem;
    margin: 0.5rem;
    padding: 0.5rem 1rem;
    background-color: lightblue;
}
```

5. Now let's understand what are the steps that UI renders (Mount and Unmount) (React Life Cycle Methods) in React app.
```typescript jsx
import React, {Component} from "react";
import './Counter.css';

class Counter extends Component {
  constructor(props: any) {
    super(props);
    alert("Constructor: Component is initializing!")
    console.log("Constructor: Component is initializing");
  }

  componentDidMount() {
    alert("componentDidMount: Component has been mounted");
    console.log("componentDidMount: Component has been mounted");
  }

  componentWillUnmount() {
    alert("componentWillUnmount: Component is being removed")
    console.log("componentWillUnmount: Component is being removed");
  }

  render() {
    return (
      <div className="container">
        <h1>React Counter (Class Component)</h1>
        <h2>Count: 0</h2>
        <div>
          <button className="button">+</button>
          <button className="button">-</button>
        </div>
      </div>
    );
  }
}

export default Counter;
```

Here, you need to pass the props in `App.tsx`:
```typescript jsx
render() {
    return (
        <div className="App">
            <Counter data={"Hello"}/>
        </div>
    );
}
```

6. Let's have a look at the other Lifecycle Method componentDidUpdate (With state updates)
```typescript jsx
import React, {Component} from "react";
import './Counter.css';

interface CounterAppProps {
  data: any
}
interface CounterAppState {
  count: number
}

class Counter extends Component<CounterAppProps, CounterAppState> {
  constructor(props: CounterAppProps) {
    super(props);
    this.state = {
      count: 0,
    };
    alert("Constructor: Component is initializing!")
    console.log("Constructor: Component is initializing");
  }

  componentDidMount() {
    alert("componentDidMount: Component has been mounted! Received props:" + this.props.data)
    console.log("componentDidMount: Component has been mounted");
  }

  componentDidUpdate(prevProps: CounterAppProps, prevState: CounterAppState) {
    if (prevState.count !== this.state.count) {
      alert("componentDidUpdate: Count has been updated")
      console.log("componentDidUpdate: Count has been updated");
    }
  }

  componentWillUnmount() {
    alert("componentWillUnmount: Component is being removed")
    console.log("componentWillUnmount: Component is being removed");
  }

  increment = () => {
    this.setState((prevState) => ({
      count: prevState.count + 1,
    }));
  };

  decrement = () => {
    this.setState((prevState) => ({
      count: prevState.count - 1,
    }));
  };

  render() {
    return (
      <div className="container">
        <h1>React Counter (Class Component)</h1>
        <h2>Count: {this.state.count}</h2>
        <div>
          <button onClick={this.increment} className="button">+</button>
          <button onClick={this.decrement} className="button">-</button>
        </div>
      </div>
    );
  }
}

export default Counter;
```
Define props in `Counter.tsx` as optional if it's not mandatory:

```typescript jsx
interface CounterAppProps {
  data?: any // like this using ? mark
}
```