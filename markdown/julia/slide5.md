### SUMMARY
```javascript
const basicHookReducer = (newState, action) => {
    return typeof action === 'function' 
    ? action(newState) 
    : newState
  }

// 
const resolveDispatcher = (() => {
    let _state;

    const useState = (initialState) => {
        let state = _state || initialState;
        const setState = (newState, action) => {
            _state = basicHookReducer(newState, action);
        }
        return [state, setState]
    }

    const render = (Component) => {
        const fiber = Component();
        fiber.render();
        return fiber;
    }

    return { 
        useState, 
        render, 
        //... 
    };
})();

const useState = (initialState) => {
    const dispatcher = resolveDispatcher;
    return dispatcher.useState(initialState);
}

const render = (Component) => {
    const dispatcher = resolveDispatcher;
    return dispatcher.render(Component);
}

const Counter = () => {
    const [count, setCount] = useState(1);
    return {
        render: () => console.log(count),
        click: () => setCount(count + 1)
    }
}

// Simulating app on reload
let app = render(Counter);

// Simulating a click in the app
app.click();
app = render(Counter);

// Simulating another click in the app
app.click();
app = render(Counter);
```
https://github.com/zerodeleo/hooks-under-the-hoods