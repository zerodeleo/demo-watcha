### Functional Component
```jsx
const Counter = () => {
  const [count, setCounter] = useState(0);

  const handleDecrement = () => setCounter(count - 1);

  const handleIncrement = () => setCounter(count + 1);

  return (
    <div>
      <button onClick={handleDecrement}> - </button>
      <button onClick={handleIncrement}> + </button>
    </div>
  );
};
```