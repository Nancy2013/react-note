<!--
 * @Author: your name
 * @Date: 2020-11-09 10:47:11
 * @LastEditTime: 2020-11-10 15:32:38
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: \react-note\issues.md
-->

# React

## state

- 这里的合并是浅合并，所以 this.setState({comments}) 完整保留了 this.state.posts， 但是完全替换了 this.state.comments，最终什么效果

## 事件

```html
<!-- 事件参数，有什么区别 -->
<button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
<button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
```

## 路由

## 高阶组件

## Hook

## Redux
