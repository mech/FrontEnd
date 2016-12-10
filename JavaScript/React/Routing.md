# Routing

* [RR4 docs](https://react-router.now.sh/)
* [Simple declarative Redux state with React Router 4 server side rendering](https://medium.com/@AlexFaunt/satisfying-your-apps-state-343118b0730d#.gh5ihu9ii)

Starting from v4, routes are just components. The components now define the composition of the UI. Before all your routes may be in `index.js`:

```js
ReactDOM.render(
  <Provider store={store}>
    <Router history={browserHistory}>
      <Route path="/" component={HomeContainer} />
      <Route path="/r/:name" component={SubredditContainer} />
    </Router>
  </Provider>
)
```

In v4, you need to replace your `props.children` (outlets) with several matches/screens that you intend to have:

```js
const App = (props) => {
  <BrowserRouter>
    <div class="container">
      <Match exactly pattern="/" component={HomeContainer} />
      <Match exactly pattern="/r/:name" component={SubredditContainer} />
    </div>
  </BrowserRouter>
}
```

## Code splitting

* [DIY](https://twitter.com/ryanflorence/status/775743520615206913)