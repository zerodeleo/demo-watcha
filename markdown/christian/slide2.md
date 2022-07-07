### Class Component

```JSX
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0,
    };
  }

  decrement() {
    this.setState(prevState => (prevState <= 0 ? 0 : ({ count: prevState.count - 1 })));
  }

  increment() {
    this.setState(prevState => ({ count: prevState.count + 1 }));
  }

  render() {
    return (
      <div>
        <button onClick={e => this.decrement(e)}>-</button>
        <button onClick={e => this.increment(e)}>+</button>
      </div>
    );
  }
}
```