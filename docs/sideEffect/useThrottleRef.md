## 简介
一个帮你处理生产一个`throttle`过的代理新`Ref`
> 1. 可自动在组件卸载时清除事件监听  
> 2. 以`ref`形态返回数据
> 3. 以正常对`rawRef`访问方式即可自动`throttle`新的代理`Ref`

## 代码演示
#### 基本使用  
---
<use-throttle-ref />
#### 代码  
---
```vue
<template>
  <div>
    <input type="text" @input="(e) => (rawRef = e.target.value)" />
    <div class="block">throttle Ref: {{ throttleRef }}</div>
  </div>
</template>
<script>
import { ref } from '@vue/composition-api'
import { useThrottleRef } from '@xuguo/vue-hooks'
export default {
  name: 'use-throttle-ref',
  setup() {
    const rawRef = ref('')
    const throttleRef = useThrottleRef(rawRef, 500)
    return {
      throttleRef,
      rawRef,
    }
  },
}
</script>
```


## API  
```ts
const throttleRef = useThrottleRef(rawRef, wait):
```

### RetrunValue
| 参数 | 说明 | 类型 |
| --- | --- | --- |
| `throttleRef` | 代理`rawRef`的新`Ref`对象 | `Ref<UnwrapRef<typeof rawRef>>` |

### Params
| 参数 | 说明 | 类型 |
| --- | --- | --- |
| `rawRef` | 原始的`Ref`对象 | `Ref` |
| `wait` | throttle的时长 | `number` |