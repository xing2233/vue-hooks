## 简介
一个帮你处理点击事件发生在指定元素外的`hooks`
> 1. 可自动在组件卸载时清除事件监听  
> 2. 可直接采用`ref`方式监听`Dom`事件

## 代码演示
#### 基本使用  
<use-click-outside />
#### 代码  
::: details 点击查看代码
<<< @/docs/.vuepress/components/useClickOutside.vue
:::


## API  
```ts
<button ref="elRef">some text</button>

const elRef = useClickOutside(handler, dom?)
```

#### RetrunValue
| 参数 | 说明 | 类型 |
| --- | --- | --- |
| `elRef` | 一个指定事件绑定元素的`ref`对象 | `Ref<null | HTMLElement>` |

#### Params
| 参数 | 说明 | 类型 |
| --- | --- | --- |
| `handler` | 监听事件的回调函数 | `(evt: MouseEvent) => any` |
| `dom` | 需要检测的`Dom` | `HTMLElement | (() => HTMLElement)` |
