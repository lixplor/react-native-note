# Flexbox布局

* React Native使用`Flexbox`规则制定某个组件的子元素的布局.
    - Flexbox可以在不同屏幕尺寸上提供一致的布局
* 主要包括
    - `flexDirection`
    - `alignItems`
    - `justifyContent`
* 注意, React Native中的`flexDirection`默认值是`column`而不是`row`, 而`flex`也只能制定一个数字值


## flexDirection

* `flexDirection`决定布局的**主轴**
    - `row`: 水平轴从左向右, 子元素按照水平轴排列
    - `row-reverse`: 水平轴从右向左
    - `column`: 竖直轴从上向下, 子元素按照数值轴排列. **默认值**
    - `column-reverse`: 竖直轴从下向上

```javascript
import React, { Component } from 'react';
import { AppRegistry, View } from 'react-native';

class FlexDirectionBasics extends Component {
  render() {
    return (
      // 尝试把`flexDirection`改为`column`看看
      <View style={{flex: 1, flexDirection: 'row'}}>
        <View style={{width: 50, height: 50, backgroundColor: 'powderblue'}} />
        <View style={{width: 50, height: 50, backgroundColor: 'skyblue'}} />
        <View style={{width: 50, height: 50, backgroundColor: 'steelblue'}} />
      </View>
    );
  }
};

AppRegistry.registerComponent('AwesomeProject', () => FlexDirectionBasics);
```


## justifyContent

* `justifyContent`决定子元素沿着主轴的排列方式
    - `flex-start`: 起始端
        - `|oo    |`
    - `center`: 居中
        - `|  oo  |`
    - `flex-end`: 末尾端
        - `|    oo|`
    - `space-between`: 两端对齐, 两端组件靠边, 中间间隙和组件平均分布
        - `|o  o  o  o|`
    - `space-around`: 间隙和组件平均分布
        - `| o o o o |`

## alignItems

* `alignItems`决定子元素延`次轴(与主轴垂直的轴)`的排列方式
    - `flex-start`: 起始端
    - `center`: 居中
    - `flext-end`: 末尾端
    - `stretch`: 拉伸充满空间(如果空间可以拉伸的话)

## flexWrap

* `flexWrap`决定子控件的换行方式
    - `nowrap`: 到屏幕边界后不换行
    - `wrap`: 到屏幕边界后向下换行
    - `wrap-reverse`: 到屏幕边界后向上换行

## alignContent

* `alignContent`决定子控件换行的间距
    - `stretch`: 拉伸子控件充满屏幕
    - `flex-start`: 居上
    - `center`: 居中
    - `flex-end`: 居下
    - `space-between`: 两端靠边, 中间间隙和组件平均分布
    - `space-around`: 间隙和组件平均分布


> [更多布局](http://reactnative.cn/docs/0.40/layout-props.html)
