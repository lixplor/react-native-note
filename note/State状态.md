# State状态

* 一个组件有两种数据: `props`和`state`
    - `props`是在父控件中指定的, 且一经指定, 在被指定的组件的生命周期中则不再改变
    - `state`是在组件的构造器中初始化的, 可以通过`setState()`改变数据
    - 举例:
        - `props`: 一个组件有闪烁文字, 文字在组件创建时已经指定, 应该用`props`
        - `props`: 一个组件有闪烁文字, 文字闪烁的显隐状态时随时间变化的, 应该用`state`

```javascript
import React, { Component } from 'react';
import { AppRegistry, Text, View } from 'react-native';

class Blink extends Component {
  constructor(props) {
    super(props);
    this.state = { showText:true };
 
    // 每1000毫秒对showText状态做一次取反操作
    setInterval( () => {
      this.setState({ showText:!this.state.showText });
    }, 1000);
  }

  render(){
    // 根据当前showText的值决定是否显示text内容
    let display = this.state.showText? this.props.text : '';
    return (
      <Text>{display}</Text>
    );
  }
}

class BlinkApp extends Component {
  render() {
    return (
      <View>
        <Blink text='I love to blink' />
        <Blink text='Yes blinking is so great' />
        <Blink text='Why did they ever take this out of HTML' />
        <Blink text='Look at me look at me look at me' />
      </View>
    );
  }
}

AppRegistry.registerComponent('BlinkApp', () => BlinkApp);
```
