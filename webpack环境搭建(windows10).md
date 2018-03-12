# webpack环境搭建(windows 10)

1.安装npm，访问 <https://nodejs.org/en/download/>  下载nodejs。

2.打开64位的cmd 输入命令node --version查看版本。（64位的cmd在C:\Windows\SysWOW64\cmd.exe）。

3.cmd进入到项目目录,输入
>npm init

 初始化一个node项目s输入项目名称等信息,完成后生成一个package.json文件.

4.项目中安装webpack
 >npm install --save-dev webpack

 >npm install webpack-cli

5.需要一个webpack.config.js文件，记录webpack配置信息。配置如下

```javascript
var webpack = require('webpack');
var path = require('path');
var buildPath = path.resolve(__dirname, 'build');
var config = {
//入口文件
entry: {
  index : './src/scripts/index.js'
},
//extensions: ['', '.js', '.json', '.css', '.less'],
output: {
  path: buildPath,    //编译后的文件路径
  filename: 'app.js'
},
module: {


},
};

module.exports = config;
```

6.新建一个src和build目录， src放源代码t版，css，js.build是编译后的源文件,src/scripts/index.js文件作为我们的入口文件

7.输入webpack命令既可以得到编译后的文件build/app.js，然后在自己的html中引用这个js文件。

8.webpack常用命令

>webpack --watch       // 自动编译

>webpack -p               // 压缩混淆代码

>webpack --config ***.js   // 替换掉默认的webpack.config.js配置文件名称

1.[makedown官网](https://github.com/DavidAnson/markdownlint/blob/v0.7.0/doc/Rules.md)
