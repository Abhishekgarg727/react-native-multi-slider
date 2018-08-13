# npm install --save abhishekgarg727/react-native-multi-slider

Pure JS react native slider component with one or two markers.
Options to customize track, touch area and provide customer markers and callbacks for touch events and value changes.

## Examples

```
cd example
npm install
react-native run-ios
react-native run-android
```

![Example](https://raw.githubusercontent.com/ptomasroos/react-native-multi-slider/master/docs/demo.gif)


## Getting Started

- [Installation](#installation)

### Installation

```bash
$ npm install --save abhishekgarg727/react-native-multi-slider
```

### Props with Examples

```
// both for multi  and single slider

pressed: {true}
markerStyle= {{
  //ios only
        height: 30,
        width: 30,
        borderRadius: 30,
        borderWidth: 1,
        borderColor: '#DDDDDD',
        backgroundColor: '#FFFFFF',
        shadowColor: '#000000',
        shadowOffset: {
          width: 0,
          height: 3,
        },
        shadowRadius: 1,
        shadowOpacity: 0.2,
      
     // android only
        height: 12,
        width: 12,
        borderRadius: 12,
        backgroundColor: '#0D8675',
}
    
pressedMarkerStyle= {
        height: 20,
        width: 20,
        borderRadius: 20,
   }
enabled: {true}
selectedStyle={{
  backgroundColor: 'gold',
}}
unselectedStyle={{
  backgroundColor: 'silver',
}}
values={[5]}
containerStyle={{
  height:40,
}}
trackStyle={{
  height:10,
  backgroundColor: 'red',
}}
touchDimensions={{
  height: 40,
  width: 40,
  borderRadius: 20,
  slipDisplacement: 40,
}}
customMarker={CustomMarker}
sliderLength={280}

// Multi marker only
allowOverlap={false}
snapped={true}
min={100}
max={3000}
```


### Usage in a ScrollView

```
 enableScroll = () => this.setState({ scrollEnabled: true });
 disableScroll = () => this.setState({ scrollEnabled: false });
 
 render() {
   return (
     <ScrollView scrollEnabled={this.state.scrollEnabled}>
      <MultiSlider
        ...
        onValuesChangeStart={this.disableScroll}
        onValuesChangeFinish={this.enableScroll}
      />
    </ScrollView>
    );
```
### shape up CustomMarker as left and right

In order to make different styles on markers you can set isMarkersSeparated to true, define customMarkerLeft and customMarkerRight in MultiSlider. for example:


```
<MultiSlider
     ...
      isMarkersSeparated={true}
      
      customMarkerLeft={(e) => {
         return (<CustomSliderMarkerLeft
          currentValue={e.currentValue}/>)
          }}
         
         customMarkerRight={(e) => {
         return (<CustomSliderMarkerRight
         currentValue={e.currentValue}/>)
         }}
     />

```
