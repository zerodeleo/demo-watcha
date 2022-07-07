### CREATING THE DISPATCHERS
```javascript
const useState = (initialState) => {
    const dispatcher = resolveDispatcher;
    return dispatcher.useState(initialState);
}

const render = (Component) => {
    const dispatcher = resolveDispatcher;
    return dispatcher.render(Component);
}
```