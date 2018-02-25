# webpack
### 开始
使用webpack通过以下命名安装
```
//初始化
npm init
//安装为开发依赖
npm install webpack --save-dev 
```
安装完成通过新建一个`webpack.config.js`来配置我们的项目，通常里面是导出一个对象的形式
```
module.exports = {
  //配置选项
}
```
### 入口
`entry`字段表示入口文件，入口是webpack建立依赖关系的主文件，webpack会找到入口文件中依赖的其他模块。在`webpack.config.js`中配置
```
module.exports = {
  //单个入口文件
  entry: './main.js'
}
```
一般指定单个入口文件，如果指定多个入口文件就要写成对象的形式
```
module.exports = {
  entry: {
    bundle1: './main1.js',
    bundle2: './main2.js'
  }
}
```
