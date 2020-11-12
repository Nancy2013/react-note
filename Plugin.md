<!--
 * @Author: your name
 * @Date: 2020-11-12 14:14:35
 * @LastEditTime: 2020-11-12 14:15:09
 * @LastEditors: your name
 * @Description: In User Settings Edit
 * @FilePath: \react-note\Plugin.md
-->

# Plugin

## 第三方库引用

```javascript
class SomePlugin extends React.Component {
  componentDidMount() {
    this.$el = $(this.el);
    this.$el.somePlugin();
  }

  componentWillUnmount() {
    this.$el.somePlugin('destroy');
  }

  render() {
    return <div ref={(el) => (this.el = el)} />;
  }
}
```
