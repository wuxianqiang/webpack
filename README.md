# webpack
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
`entry`字段表示入口文件，入口是webpack建立依赖关系的主文件，webpack会找到入口文件中依赖的其他模块
```
module.exports = {
  entry: './main.js'
}
```
一般指定单个入口文件，如果指定多个入口文件导出到一个项目文件中，我们以数组的形式
```
module.exports = {
  entry: [
    './main1.js',
    './main2.js'
  ]
}
```
在多页面应用中还有按需加载的情况，这时候你就要与对象的形式，根据指定的入口文件输出到指定的页面
```
module.exports = {
  entry: {
    bundle1: './main1.js',
    bundle2: './main2.js'
  }
}
```
## 出口
在 webpack 中配置 output 属性的最低要求是，将它的值设置为一个对象，包括两点：`filename` 用于输出文件的文件名。 `path`输出目录的绝对路径。
```
module.exports = {
  entry: './main.js',
  output: {
    filename: 'bundle.js'
    path: require('path').resolve('/dist')
  }
};
```
`path`里面的路径是绝对路径，我们可以导入导入node中`path`默认使用`resolve`方法传入一个相对路径来转为为绝对路径。
`filename`是指定输出后的文件夹名字，这里写的是`bundle.js`，当然你也可以根据指定的文件名来输出就可以这样写`[name.js]`，其中name表示占位符，文件名是不变，如果要根据文件的内容变化来输出到不同的文件中，就可以使用hash占位符


如果你与多个文件分别进行输出的时候，这时候使用站位符就非常的合适
```
module.exports = {
  entry: {
    bundle1: './main1.js',
    bundle2: './main2.js'
  }
  output: {
    filename: '[name].js'
    path: require('path').resolve('/dist')
  }
};
```
