# Higher Order Components

* [HOC: A React Application Design Pattern from SitePoint](https://www.sitepoint.com/react-higher-order-components/)

```js
const withPlayQueue = (component) => class PlayQueue extends React.Component {
  state = {
    isPlaying: false,
    playQueue: [],
    currentTrack: -1
  }
  
  addTrack = (track) => this.setState({
    playQueue: this.state.playQueue.concat(track)
  })
  
  render() {
    const playQueue = {
      addTrack: this.addTrack
    }
    
    return (
      <View>
        <Player />
        <Component playQueue={playQueue} {...this.props} />
      </View>
    )
  }
}

const App = () => { ... }
module.exports = withPlayQueue(App)

```