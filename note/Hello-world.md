# Hello world程序

* React native很像React, 但基础组件是原生组件, 而不是web组件
* 使用React native需要了解一些React概念, 如`JSX`, `组件`, `状态(state)`, `属性(props)`


## Hello world

```javascript
import React, { Component } from 'react';
import { AppRegistry, Text } from 'react-native';

class HelloWorldApp extends Component {     // 定义一个组件
  render() {
    return (
      <Text>Hello world!</Text>
    );
  }
}

// 注意，这里用引号括起来的'HelloWorldApp'必须和你init创建的项目名一致
AppRegistry.registerComponent('HelloWorldApp', () => HelloWorldApp);   // 将定义的组件注册
```

代码解释:
* 文件后缀为`.js`, 是一个JS文件, 但语法使用了`JSX`和`ES6`
    - `import`, `from`, `class`, `extends`, `() =>`都是ES6语法
    - `<Text>Hello world!</Text>`是JSX语法, `Text`是一个内置的用于显示文本的组件
* 通过定义类, 继承`Component`类的方式, 定义了一个名为`HelloWorldApp`的组件
* 使用`AppRegistry`模块进行了注册, 该模块告知React Native哪一个组件要被注册为整个应用的根容器, 一般`AppRegistry.registerComponent`方法之调用一次


* [ES5/ES6语法对照表](http://bbs.reactnative.cn/topic/15/react-react-native-%E7%9A%84es5-es6%E5%86%99%E6%B3%95%E5%AF%B9%E7%85%A7%E8%A1%A8)
