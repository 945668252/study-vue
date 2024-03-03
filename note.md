#初始化
npm create vue@latest

#3-3
createApp是引入的花盆，App的作为根的花
mount摆放方法
createApp(App).mount('#app')，把根插在花盆后摆放在id为app的容器
## 安装setup语法糖插件
npm i vite-plugin-vue-setup-extend -D
在vite.config.ts中引入这个模块
作用：可以写成一个script标签，组件名直接写在name上。标签内必须有内容，可加注释，否则报错

##自动补齐.value
商店下载volar插件
vscode插件中找到设置，用户，额外设置，勾上：dot not value