Select 组件
===

### Select Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| selectStyle | 选中样式 | string | borderStyle/iconStyle | - |
| selectOne | 是否为单选 | boolean | — | true |
| radioList | 选项数组 | array | — | — |
| isRow | 选项是否排列在一行 | boolean | — | true |
| isRadio | 选项是否为圆形 | boolean | — | true |
| maxLimit | 最多选中个数 | number | - | - |
|radioList.index | 选项标志 | string | — | — |
| radioList.checked | 是否选中 | boolean | — | false |
| radioList.value | 选项对应的值 | string | — | — |
| radioList.label | 选项标签 | string | — | — |

### Select Events
| 事件名称 | 说明 | 回调参数 |
| --- | --- | --- |
| select | 点击select触发的事件 | index,value |
