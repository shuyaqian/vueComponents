weex-ui-components
===

A ui-components webpack for weex.


Usage
---

已有组件：

button/button-group/button-icon/button-plain/cell-item/cells-item/col/form-item/icon/input/line/list/menu/picker/row/search/select/slider/switch/tab/tabbar/textarea/textarea-withcount/upload

使用方法：按需引入 


Each component attributes as follows：
===


1.Button 组件
---

按钮组件，以下分别是基本按钮、朴素按钮、图标按钮的属性说明：

#### Button Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| size | 尺寸 | string | large,small | — |
| type | 类型 | string | primary,secondary,warning,text | — |
| disabled | 是否禁用状态 | boolean | — | false |

#### Plain Button Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| size | 尺寸 | string | large,small | — |
| type | 类型 | string | primary,secondary,warning | — |
| disabled | 是否禁用状态 | boolean | — | false |

#### Icon Button Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| size | 尺寸 | string | large,small | — |
| type | 类型 | string | primary,secondary,warning,text | — |
| disabled | 是否禁用状态 | boolean | — | false |
| icon | 图标，已有的图标库中的图标名 | string | [Icon List](http://iconfont.cn/manage/index?manage_type=myprojects&spm=a313x.7781069.1998910419.9.O5ebs4&projectId=289828&keyword=) | — |

2.Cell-item 组件
---

类似于form的列表视图，用于将信息以列表的结构显示在页面上，属性说明如下:

#### Cell-item Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| access | 是否有图标 | boolean | — | false |
| last | 是否为最后一列 | boolean | — | false |
| cellIcon | 图标 | string | — | — |
| title | 标题文字 | string | — | — |
| desc | 说明文字 | string | — | — |

3.Cells-item组件
---
列表视图集合，属性说明如下:

#### Cell-item Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| title | 列表标题 | string | — | — |

4.Col组件
---
栅格布局组件，属性说明如下:

#### Col Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| span | 栅格占据的列数 | number | — | - |

5.Form-cell组件
---
由输入框、选择器、单选框、多选框等控件组成，用以收集、校验和提交数据。属性说明如下:

#### Form Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| inline | 是否在同一行 | boolean | — | true |
| align | 排列方式 | string | — | left |
| label | 标签 | string | — | — |
| width | 用于计算标签宽度 | number | — | — |
| last | 是否为最后一列| boolean | — | false |

6.Gallery组件
---
#### Gallery Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| index | 图片标志 | string | — | — |
| galleryImgSrc | 图片路径 | string | — | — |

7.Icon组件
---
图标更新步骤:
1.登录http://www.iconfont.cn/plus
2.找到想添加的图标添加至项目vue-com
3.更新Unicode的在线链接
4.将icon.vue文件中的url('//at.alicdn.com/t/***.ttf')替换掉
5.在icon.data.js中添加图标的名称和对应的code，搞定！

#### Icon Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| name | 图标名称 | string | — | — |

8.input组件
---
#### Input Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| type | 类型 | string | text/password/url/email/tel | text |
| value | 绑定值 | string, number | — | — |
| maxlength | 最大输入长度 | number | — | — |
| placeholder | 输入框占位文本 | string | — | — |
| disabled | 禁用 | boolean | — | false |
| autofocus | 原生属性，自动获取焦点 | boolean | true, false | false |

#### Input Events
| 事件名称 | 说明 | 回调参数 |
| --- | --- | --- |
| blur | 在 Input 失去焦点时触发 | (event: Event) |
| focus | 在 Input 获得焦点时触发 | (event: Event) |
| change | 在 Input 值改变时触发 | (value: string \| number) |

9.Line组件
---
宽度为1的白色分隔线

10.List组件
---
分为纯文字无序列列表、图文混排列表、有序列表、节点列表。属性说明如下:

#### List Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| hasseq | 是否有序列 | boolean | — | false |
| hasnode | 是否有节点 | boolean | — | false |
| imgSrc | 图片路径 | string | — | — |
| itemTitle | 列表名称 | string | - | - |
| itemContent | 列表内容 | string | - | - |
| inline | 名称时间状态是否在一行上| boolean | - | - |
| itemName | 名字 | string | - | - |
| nameColor | 名字颜色 | string | - | - |
| itemSize | 名字字体大小 | number | - | - |
| itemTime | 时间 | string | - | - |
| timeColor | 时间颜色 | string | - | - |
| timeSize | 时间字体大小 | number | - | - |
| itemStatus | 状态 | string | - | - |
| starusColor | 状态颜色 | string | - | - |
| starusSize | 状态字体大小 | number | - | - |

11.Picker 组件
---
#### Picker Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| type | picker 的类型 | string | date,time | date |
| placeholder | 占位文本 | string | — | 请选择 |
| value | 绑定值 | string | date 类型时格式为 `yyyy-mm-dd`; time 类型时格式为 `hh:mm` | — |

#### Picker Events
| 事件名称 | 说明 | 回调参数 |
| --- | --- | --- |
| select | 点击data选择器触发的事件 | 选中的data值 |

12.Row 组件
---
#### Row Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| gutter | 栅格间隔 | number | — | 0 |
| justify | `flex` 布局下的水平排列方式 | string | start/end/center/space-around/space-between | start |
| align | `flex` 布局下的垂直排列方式 | string | top/middle/bottom | top |

13.Search组件
---
搜索框组件

#### Search Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |

14.Select 组件
---
#### Select Attributes
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

#### Select Events
| 事件名称 | 说明 | 回调参数 |
| --- | --- | --- |
| select | 点击select触发的事件 | index,value |

15.Slider 轮播组件
---
#### Select Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| interval | 切换时间(ms) | number | - | - |
| autoPlay | 是否自动播放 | boolean | — | true |
| imageList | 图片列表 | array | — | — |
| indicatorColor | 导航颜色 | string | — | - |
| indicatorLeft | 导航距左侧距离 | number | — | - |

16.Switch 组件
---
#### Switch Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| checked | 是否选中 | boolean | — | false |
| disabled | 是否禁用 | boolean | — | false |

#### Events
| 事件名称 | 说明 | 回调参数 |
| --- | --- | --- |
| change | switch 状态发生变化时的回调函数 | 新状态的值 |

17.Tab组件
---
由横向和垂直tab组成, 属性说明如下:

#### Tab Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| inline | 是否在同一行 | boolean | — | true |
| tabWidth | 纵向tab的宽度设置 | number | — | - |
| selectedColor | 选中颜色 | string | - | - |
| tabList | 标签内容| array | — | - |

18.Tabbar组件
---
底部导航栏, 属性说明如下:

#### Tab Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| tabitem | tab参数 | array | — | — |
| tabitem[].title | tab名称 | string | — | — |
| tabitem[].icon | icon名称 | string | — | — |
| tabitem[].visibility | tab是否被选择 | boolean | — | — |
| itemstyle | 样式参数 | object | — | — |
| itemstyle.titleColor | 名称颜色 | string | — | — |
| itemstyle.selectedTitleColor | 被选中后名称颜色 | string | — | — |
| itemstyle.iconColor | 图标颜色 | string | — | — |
| itemstyle.selectedIconColor | 被选中后图标颜色 | string | — | — |

19.Textarea
---
#### Textarea Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| value | 绑定值 | string, number | — | — |
| maxlength | 最大输入长度 | number | — | — |
| placeholder | 输入框占位文本 | string | — | — |
| disabled | 禁用 | boolean | — | false |
| rows | 输入框行数 | number | — | 2 |
| autofocus | 原生属性，自动获取焦点 | boolean | true, false | false |

#### Textarea Events
| 事件名称 | 说明 | 回调参数 |
| --- | --- | --- |
| blur | 在 Textarea 失去焦点时触发 | (event: Event) |
| focus | 在 Textarea 获得焦点时触发 | (event: Event) |
| change | 在 Textarea 值改变时触发 | (value: string \| number) |

20.Upload组件
---
通过点击上传图片，属性说明如下:

#### Upload Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| index | 图片标志 | string | — | — |
| title | 上传标题 | string | — | — |
| limit | 是否有数量上限 | boolean | — | false |
| uploadLimit | 上传数量上限 | number | — | 9 |
| desc | 上传解释详情 | string | — | 9 |
| uploadList | 照片路径列表 | array | — | - |
| enabled | 是否还能再上传 | boolean | — | true |
