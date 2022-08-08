# vue-cli创建Vue项目

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

## 注意

需要注意的是，采用vue-cli构建的Vue项目，项目构建后入口不是`index.html`，因此，必要的时候需要采用webpack搭建Vue项目。