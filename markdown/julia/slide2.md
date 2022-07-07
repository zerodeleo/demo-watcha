### SIMULATING A REACT COMPONENT
```javascript
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
```