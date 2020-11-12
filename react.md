<!--
 * @Author: your name
 * @Date: 2020-11-09 10:47:11
 * @LastEditTime: 2020-11-12 17:42:47
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: \react-note\issues.md
-->

# React

## state

- 这里的合并是浅合并，所以 this.setState({comments}) 完整保留了 this.state.posts， 但是完全替换了 this.state.comments，最终什么效果

```javascript
// 解决异步state不更新问题
this.setState((state, props) => ({
  counter: state.counter + props.increment,
}));
```

## event

```html
<!-- 事件参数，有什么区别 -->
<button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
<button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
```

## component

- 组件中静态方法的作用

```javascript
// 旧
class Base extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: props.initialCount };
  }
  // ...
}

// 新
class Form extends Component {
  initialState = {
    name: '',
    job: '',
  };

  state = this.initialState;
}
```

## JSX

React 组件也能够返回存储在数组中的一组元素,这里比较强大

```javascript
render() {
  // 不需要用额外的元素包裹列表元素！
  return [
    // 不要忘记设置 key :)
    <li key="A">First item</li>,
    <li key="B">Second item</li>,
    <li key="C">Third item</li>,
  ];
}
```

## context

> 适用场景：可以使用 context 实现属性的多层级广播，
> 替代方案：如果担心会对组件复用性造成影响，可以考虑在高层级组件中，将低层级组件直接作为属性传递

issues：

```javascrirpt
static contextType = ThemeContext;
```

不能直接使用`this.context`,而需要给子组件 contextType 属性赋值 Context，比较鸡肋

## 高阶组件

使用组件作为参数，纯函数，对组件进行参数化包装，返回原组件，不对组件做修改

```javascript
// 伪代码
render() {
  // 过滤掉非此 HOC 额外的 props，且不要进行透传
  const { extraProp, ...passThroughProps } = this.props;

  // 将 props 注入到被包装的组件中。
  // 通常为 state 的值或者实例方法。
  const injectedProp = someStateOrInstanceMethod;

  // 将 props 传递给被包装组件
  return (
    <WrappedComponent
      injectedProp={injectedProp}
      {...passThroughProps}
    />
  );
}
```

## PureComponent

可以提高渲染性能，减少不必要渲染，但是对 state 及 props 浅比较

```javascript
// 解决方案，返回新对象
this.setState((state) => ({
  words: state.words.concat(['marklar']),
}));

function updateColorMap(colormap) {
  return Object.assign({}, colormap, { right: 'blue' });
}

function updateColorMap(colormap) {
  return { ...colormap, right: 'blue' };
}
```

## Refs

- 高阶组件中 ref 的使用不太会

## Key 值作用
