input组件
===

### Input Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| type | 类型 | string | text/password/url/email/tel | text |
| value | 绑定值 | string, number | — | — |
| maxlength | 最大输入长度 | number | — | — |
| placeholder | 输入框占位文本 | string | — | — |
| disabled | 禁用 | boolean | — | false |
| autofocus | 原生属性，自动获取焦点 | boolean | true, false | false |

### Input Events
| 事件名称 | 说明 | 回调参数 |
| --- | --- | --- |
| blur | 在 Input 失去焦点时触发 | (event: Event) |
| focus | 在 Input 获得焦点时触发 | (event: Event) |
| change | 在 Input 值改变时触发 | (value: string \| number) |
