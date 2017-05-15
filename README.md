# React Native Network Graph

Component for displaying connections between entities, in the form of a network graph.

### Dependencies
```
react-native-svg
prop-types
```

The prop-types library was used for checking the component's PropTypes as recommended by Facebook [here](https://facebook.github.io/react/docs/typechecking-with-proptypes.html). The other library([react-native-svg](https://github.com/react-native-community/react-native-svg)) was used for drawing the entities. 

### Installation
```bash
npm install react-native-network-graph
```

Then run 
```bash 
rnpm link
```

## Usage

```js
import NetworkGraph from 'react-native-network-graph';
```

And then in your component:

```jsx
  constructor(props) {
    super(props);
    this.state = {
      selectedCircleIndex:0  //this can also be stored in redux store.
    };
  }

  onCircleClick(index) {  //or an action can be dispatched as well.
    this.setState({
      selectedCircleIndex:index 
    })
  }
  
  render() {
    let connections = {
      "1":[2,4], //node at index 1 is connected to nodes at index 2 and 4 respectively.
      "2":[6,7] //node at index 2 is connected to nodes at index 6 and 7 respectively.
    };
    let circleTitles = ['C1','C2', 'C3', 'C4', 'C5','C6', 'C7', 'C8', 'C9'];
    return (
      <View style={styles.container}>
        <NetworkGraph
          selectedCircleIndex={this.state.selectedCircleIndex} //so that clicks on the circles reflect results in real time.
          circleTitles={circleTitles}
          connections={connections}
          containerHeight={300}
          containerWidth={300}
          centralCircleRadius={30}
          otherCircleLinesColor="black"
          otherCirclesRadius={20}
          distanceFromCenter={100}
          onCircleClick={this.onCircleClick.bind(this)}/>
      </View>
    );
  }
```
***For more content like this, check out [my blogs]( https://crazysigma.com/blogs/).***

## Props

Name | PropType | Required | Default Value | Description
--- | --- | --- | --- | ---
selectedCircleIndex | Number | Yes | None | index of the selected circle which is drawn in the center
circleTitles | Array | Yes | None | titles of all the circles.
onCircleClick | Function | Yes | None | function that is invoked on clicking the circle
connections | Object | Yes | None | See the example usage for the data structure of the  connections Object. 
containerHeight | Number | No | 500 | height of content container inside which the graph is drawn
containerWidth | Number | No | 500 | height of content container inside which the graph is drawn
centralCircleRadius | Number | No | 60 | radius of the selected circle that is to be drawn in the center
otherCirclesRadius | Number | No | 35 | radius of all the unselected circles.
distanceFromCenter | Number | No | 200 | distance of other circles from the central one. If this exceeds containerHeight and containerWidth, the graph will be cropped to fit inside the content container view.
selectedCircleLinesColor | String | No | #f59f02 | color of the lines emitting from the selected circle
otherCircleLinesColor | String | No | white | color of the lines emitting from unselected circles
centralCircleStrokeColor | String | No | #24a195 | border color of the selected circle
centralCircleFillColor | String | No | #18B0A2 | background color of the selected circle
centralCircleTextColor | String | No | white | color of the text rendered inside the selected circle
otherCircleTextColor | String | No | white | color of the text rendered inside the unselected circles
otherCircleFillColor | String | No | black | background color of the unselected circles

## License
MIT
