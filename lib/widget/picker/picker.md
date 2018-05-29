Picker 组件
===

### Picker Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| type | picker 的类型 | string | date,time | date |
| placeholder | 占位文本 | string | — | 请选择 |
| value | 绑定值 | string | date 类型时格式为 `yyyy-mm-dd`; time 类型时格式为 `hh:mm` | — |

### Picker Events
| 事件名称 | 说明 | 回调参数 |
| --- | --- | --- |
| select | 点击data选择器触发的事件 | 选中的data值 |
