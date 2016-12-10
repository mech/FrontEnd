# Forms for React

* [Controlled and uncontrolled form inputs in React don't have to be complicated](http://goshakkk.name/controlled-vs-uncontrolled-inputs-react/)
* [Should you store your form state in Redux?](http://goshakkk.name/should-i-put-form-state-into-redux/)

## Validation

* [react-validation-decorator - based on Joi](https://github.com/minhtranite/react-validation-decorator)
* [The Joi of Validation](http://vawks.com/blog/2014/03/22/the-joi-of-validation/)

## Event Handlers

Have one function just for handling the event and another for performing operation. This is so that you can reuse the operation elsewhere.

```js
handleFormSubmit(timer) {
  this.createTimer(timer)
}

createTimer(timer) {
  const t = new Timer(timer)
  this.setState({
    timers: this.state.timers.concat(t)
  })
}
```

## Using Refs

```js
handleSubmit() {
  this.props.onSubmit({
    title: this.refs.title.value
  })
}

render() {
  return (
    <input type="text" ref="title" defaultValue={this.props.title}>
  )
}
```