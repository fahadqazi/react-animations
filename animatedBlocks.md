## Animated Bloks

```javascript
import React from 'react';
import { StyleSheet, Text, View, Button, Animated, Easing, TouchableWithoutFeedback } from 'react-native';

export default class App extends React.Component {

  componentWillMount(){
    this.animatedValue1 = new Animated.Value(100);
    this.animatedValue2 = new Animated.Value(100);
  }

  componentDidMount(){
    Animated.timing(this.animatedValue1, {
      toValue: 200,
      duration: 2000,
      easing: Easing.bounce
    }).start();
    Animated.timing(this.animatedValue2, {
      toValue: 200,
      duration: 2000,
      easing: Easing.bounce
    }).start();
  }


  render() {
    const animatedHeight = { height: this.animatedValue1 }
    const animatedWidth = { width: this.animatedValue2 }
    return(
      <View style={styles.container}>
        <Animated.View style={[styles.box1, animatedHeight]}></Animated.View>
        <Animated.View style={[styles.box2, animatedWidth]}></Animated.View>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
  box1: {
    width: 100,
    height: 100,
    backgroundColor: 'black'
  },
  box2: {
    width: 100,
    height: 100,
    backgroundColor: 'red'
  }
});
```