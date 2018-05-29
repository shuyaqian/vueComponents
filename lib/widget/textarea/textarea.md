Textarea
===

### Textarea Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| value | 绑定值 | string, number | — | — |
| maxlength | 最大输入长度 | number | — | — |
| placeholder | 输入框占位文本 | string | — | — |
| disabled | 禁用 | boolean | — | false |
| rows | 输入框行数 | number | — | 2 |
| autofocus | 原生属性，自动获取焦点 | boolean | true, false | false |

### Textarea Events
| 事件名称 | 说明 | 回调参数 |
| --- | --- | --- |
| blur | 在 Textarea 失去焦点时触发 | (event: Event) |
| focus | 在 Textarea 获得焦点时触发 | (event: Event) |
| change | 在 Textarea 值改变时触发 | (value: string \| number) |
