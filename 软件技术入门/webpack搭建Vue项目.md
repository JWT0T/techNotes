# webpack搭建

1. 空文件夹下

   `npm init`

2. 安装vue和webpack相关的dependency

   * vue
   * vue-loader
   * webpack
   * webpack-dev-server
   * html-webpack-plugin

3. 目录结构

   > * node_modules
   >
   > * public
   >   * index.html
   > * src
   >   * app.vue
   >   * main.js
   > * package.json
   > * package-lock.json
   > * webpack.config.js

`main.js`

```js
import {createApp} from "vue";
import App from './app'
const app = createApp(App)
app.mount('#app')
```

`index.html`

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="app"></div>
</body>
</html>
```

`webpack.config.js`

```
const path = require('path');
const {VueLoaderPlugin} = require('vue-loader')
const HtmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
    mode:'development',
    devtool:'source-map',
    entry:'./src/main.js',
    output:{
        path:path.resolve(__dirname,'dist'),
        filename:'main.js'
    },
    watch: true,
    module:{
        rules:[
            {
                test:/\.vue$/,
                loader:'vue-loader'
            },
        ]
    },
    plugins:[
        new VueLoaderPlugin(),
        new HtmlWebpackPlugin({template:'./public/index.html'}), //JS或者CSS文件可以自动引入到html中
    ],
    resolve: {
    	alias: {
      	"@": path.resolve('src')
    	},
    	extensions: ['.js', '.css', '.vue', '.png', '.jpeg'],  //配置后缀名
    },
    devServer: {
        port:8080,
        hot:true,
        open:true,
        static: {
            directory: path.join(__dirname, './'),
            watch: true
        }
    }
}
```

`package.json`

```
"scripts": {
  "start": "webpack-dev-server",
  "build": "webpack"
}
```

## 关于如何简写路径

在`webpack.config.js`中添加`alias`，在`import`时，即可简写为`@/components/xxx`，后缀名也可省略。

```
resolve: {
	alias: {
  	"@": path.resolve('src'),
  	"@components":path.resolve("src/components")
   },
   extensions: ['.js', '.css', '.vue', '.png', '.jpeg'],  //配置后缀名
}
```

## 关于`url-loader`

`url-loader`内部封装了`file-loader`，而`file-loader`在新版本中`esModule`默认为是`true`，即默认使用ES模块语法。

```
module: {
  rules: [
    {
      test: /\.(jpe?g|png)$/,
      loader: 'url-loader',
      options: {
        limit: 10240,
        esModule: false
      }
    }
  ]
}
```

