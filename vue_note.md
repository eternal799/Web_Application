#### 配置环境

- 官网

> https://vuejs.org/

- 终端

> Linux和Mac直接用终端
>
> Windows上用powershell或者cmd，git bash有点不兼容

- 安装Node.js

```
https://nodejs.org/en/
```

- 安装@vue/cli

> 打开git bash，执行

```
npm i -g @vue/cli
```

- 启动vue自带的图形化项目管理界面（不用git bash）

```
vue ui
```

- add vue-router vuex
- bootstrap依赖
- Tasks栏
    - build
    - serve
        - 调试环境

- 把Hash去掉可以去掉#号

![image-20231118155252860](C:\Users\huadan\AppData\Roaming\Typora\typora-user-images\image-20231118155252860.png)

<img src="C:\Users\huadan\AppData\Roaming\Typora\typora-user-images\image-20231118155006949.png" alt="image-20231118155006949"/>

#### 基本概念

- 入口main.js

```vue
import { createApp } from 'vue'
import App from './App.vue'
import router from './router'
import store from './store'

createApp(App).use(store).use(router).mount('#app')
```

![image-20231118155842607](C:\Users\huadan\AppData\Roaming\Typora\typora-user-images\image-20231118155842607.png)

- vue文件三部分组成

> html+css+js
>
> scoped 不同组件的css选择器不会相互影响（有随机值 ）

- navbar+content

    - content

        > 首页 好友列表 好友动态 登录 注册 404



- 引入bootstrap

> https://v5.bootcss.com/

app.vue中

```vue
<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap/dist/js/bootstrap'
</script>
```

需安装@popperjs/core不然会报错

```
<div class="container-fluid">靠近左边
<div class="container">靠近中间
```

- JS加进来才能点得开

![image-20231119230725465](C:\Users\huadan\AppData\Roaming\Typora\typora-user-images\image-20231119230725465.png)

- 先写大的页面，页面比较大拆分成两页

- card括起来内容

- 可以将页面共有的内容做一个Base组件，slot

- 前端渲染

    > router-link
