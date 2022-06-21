# 使用 vanta.js 实现简单的页面3D动画背景

[官网地址](https://www.vantajs.com/)

[CDN](https://cdn.jsdelivr.net/npm/vanta@latest/dist/)

## 使用方式

### html 页面直接在页面进行cdn引入

```

<script src="three.r119.min.js"></script>
<script src="vanta.fog.min.js"></script>

<!-- else -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r121/three.min.js"></script>
<!-- cdn引入想要的动画 -->
<script src="https://cdn.jsdelivr.net/npm/vanta@0.5.21/dist/vanta.birds.min.js"></script>

```

![示例图片](./example.png)

### 在vue 项目中使用

- 在项目中安装 three.js 依赖

```
npm i three

```

- 在项目中安装 Vanta JS 依赖

```

npm i vanta

```

- 页面示例

```
<template>
  <div ref='vantaRef'>
    Foreground content here
  </div>
</template>
 
<script>
import * as THREE from 'three'
import BIRDS from 'vanta/src/vanta.birds'
export default {
  mounted() {
    this.vantaEffect = BIRDS({
      el: this.$refs.vantaRef,
      THREE: THREE
    })
  },
  beforeDestroy() {
    if (this.vantaEffect) {
      this.vantaEffect.destroy()
    }
  }
}
</script>

```
