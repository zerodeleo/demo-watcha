### CREATING THE RESOLVER
```javascript
const resolveDispatcher = (() => {
    const useState = (initialState) => {
        const setState = (newState, action) => {
        }
        return [state, setState]
    }

    const render = (Component) => {
    }

    return { useState, render, ... };
})();
```