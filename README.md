# webpack
### 概念
* Entry
* Output
* Loaders
* Plugins
### 开始
使用webpack通过以下命名安装
```
npm init
npm install webpack --save-dev 
```
安装完成通过新建一个`webpack.config.js`来配置我们的项目，通常里面是导出一个对象的形式
```
module.exports = {

}
```
### 入口
`entry`字段表示入口文件，入口是webpack建立依赖关系的主文件，webpack会找到入口文件中依赖的其他模块。在`webpack.config.js`中配置
```
module.exports = {
  entry: './main.js'
}
```
