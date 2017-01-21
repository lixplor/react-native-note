# Props属性

* `属性(props)`用于在组件创建时根据其参数进行定制
    - 如使用`Image`组件时, 可以闯入一个名为`source`的props来指定要显示的图片地址
* `props`也可以直接使用, 它是组件的一个属性, 且是一个对象, 可以从其中获取更多属性
* `{pic}`大括号包裹变量, 表示将`pic`这个变量引用到JSX中, 括号内部可以是一个js变量或者表达式, 会获取执行后的值

```javascript
// props示例
import React, { Component } from 'react';
import { AppRegistry, Image } from 'react-native';

class Bananas extends Component {
  render() {
    let pic = {
      uri: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Bananavarieties.jpg'
    };
    return (
      <Image source={pic} style={{width:193, height:110}} />
    );
  }
}

AppRegistry.registerComponent('Bananas', () => Bananas);
```

```javascript
import React, { Component } from 'react';
import { AppRegistry, Text, View } from 'react-native';

class Greeting extends Component {
  render() {
    return (
      <Text>Hello {this.props.name}!</Text>
    );
  }
}

class LotsOfGreetings extends Component {
  render() {
    return (
      <View style={{alignItems:'center'}}>
        <Greeting name='Rexxar' />
        <Greeting name='Jaina' />
        <Greeting name='Valeera' />
      </View>
    );
  }
}

AppRegistry.registerComponent('LotsOfGreetings', () => LotsOfGreetings);
```

