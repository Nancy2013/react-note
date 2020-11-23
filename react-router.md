<!--
 * @Author: your name
 * @Date: 2020-11-12 10:26:20
 * @LastEditTime: 2020-11-23 15:57:48
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: \react-note\react-router.md
-->

# React-router

- switch 的作用：加载 404
- routerConfig 数组中 indexRoute 含义：默认组件
- IndexLink 标签的作用

## 使用

```javascript
const routes = {
  path: '/',
  component: App,
  childRoutes: [
    { path: 'about', component: About },
    { path: 'inbox', component: Inbox },
  ],
};

React.render(<Router routes={routes} />, document.body);
```
