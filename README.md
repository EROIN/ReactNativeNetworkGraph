# React Native Network Graph

Component for displaying connections between entities, in the form of a network graph.

### Dependencies
```
react-native-svg
prop-types
```

The prop-types library was used for checking the component's PropTypes as recommended by Facebook [here](_https://facebook.github.io/react/docs/typechecking-with-proptypes.html). The other library([react-native-svg](_https://github.com/react-native-community/react-native-svg)) was used for drawing the entities. 

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

And then in your render method:

```jsx
<NetworkGraph
    selectedCircleIndex={this.state.selectCircleIndex}
    circleTitles={circleTitles}
    connections={connections}
    containerHeight={300}
    containerWidth={300}
    centralCircleRadius={30}
    otherCirclesRadius={20}
    distanceFromCenter={100}
    onCircleClick={this.onCircleClick.bind(this)}/>
```
***For more content like this, check out [my blogs]( https://crazysigma.com/blogs/).***

## Props

Name | PropType | Required | Default Value | Description
--- | --- | --- | --- | ---
selectedCircleIndex | Number | Yes | None | index of the selected circle which is drawn in the center
circleTitles | Array | Yes | None | titles of all the circles.
onCircleClick | Function | Yes | None | function that is invoked on clicking the circle
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
