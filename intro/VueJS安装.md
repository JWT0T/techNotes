# Vue.js安装

 ## 创建新的project

`vue init`

得到package.json

## 添加需要的package

`npm install vue --save-dev`

* Vue
* @vue/cli-service
* Bootstrap-vue
* Vue-template-compiler
* Vue-router

package.json中添加

```
"scripts": {
	"serve": "vue-cli-service serve",
	"build": "vue-cli-service build",
	"lint": "vue-cli-service lint",
	"start": "nodemon ./server.js"
}
```

`npm run serve`

src文件夹中创建main.js