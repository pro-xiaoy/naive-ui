# 头像组

人多不一定是好事。

```html
<n-avatar-group :options="options" :size="40" :max="3" />
<n-avatar-group :options="options" :size="40" :max="3">
  <template #avatar="{ option: { name, src } }">
    <n-tooltip>
      <template #trigger>
        <n-avatar :src="src" />
      </template>
      {{ name }}
    </n-tooltip>
  </template>
  <template #rest="{ options, rest }">
    <n-dropdown
      :options="options.map((option) => ({ key: option.name, label: option.name }))"
      placement="top"
    >
      <n-avatar>+{{ rest }}</n-avatar>
    </n-dropdown>
  </template>
</n-avatar-group>
```

```js
import { defineComponent } from 'vue'

export default defineComponent({
  setup () {
    return {
      options: [
        {
          name: '张三',
          src: 'https://gw.alipayobjects.com/zos/antfincdn/aPkFc8Sj7n/method-draw-image.svg'
        },
        {
          name: '李四',
          src: 'https://07akioni.oss-cn-beijing.aliyuncs.com/07akioni.jpeg'
        },
        {
          name: '王五',
          src: 'https://gw.alipayobjects.com/zos/antfincdn/aPkFc8Sj7n/method-draw-image.svg'
        },
        {
          name: '赵六',
          src: 'https://07akioni.oss-cn-beijing.aliyuncs.com/07akioni.jpeg'
        },
        {
          name: '七仔',
          src: 'https://gw.alipayobjects.com/zos/antfincdn/aPkFc8Sj7n/method-draw-image.svg'
        }
      ]
    }
  }
})
```