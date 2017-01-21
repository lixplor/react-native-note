# ListView

* `ListView`用于显示垂直的滚动列表, 其中元素结构相近, 仅数据不同
    - `dataSource`属性: 列表数据源
    - `renderRow`属性: 解析数据源中的数据, 然后返回一个设定好格式的组件来渲染
    - `rowHasChanged`函数: 某行数据是否变化
* ListView仅渲染屏幕上可见元素, 所以内存占用更少


``javascript
import React, { Component } from 'react';
import { AppRegistry, ListView, Text, View } from 'react-native';

class ListViewBasics extends Component {
  // 初始化模拟数据
  constructor(props) {
    super(props);
    const ds = new ListView.DataSource({rowHasChanged: (r1, r2) => r1 !== r2});
    this.state = {
      dataSource: ds.cloneWithRows([
        'John', 'Joel', 'James', 'Jimmy', 'Jackson', 'Jillian', 'Julie', 'Devin'
      ])
    };
  }
  render() {
    return (
      <View style={{flex: 1, paddingTop: 22}}>
        <ListView
          dataSource={this.state.dataSource}
          renderRow={(rowData) => <Text>{rowData}</Text>}
        />
      </View>
    );
  }
}

// 注册应用(registerComponent)后才能正确渲染
// 注意：只把应用作为一个整体注册一次，而不是每个组件/模块都注册
AppRegistry.registerComponent('ListViewBasics', () => ListViewBasics);
```

