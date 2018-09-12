## webpack V4

### 首先下载webpack 
命令： `npm install --save-dev webpack`

[创建webpack.config.js](https://webpack.js.org/guides/getting-started/#using-a-configuration)

需要安装的东西：

### babel-loader  [github教程](https://github.com/babel/babel-loader)
需要向webpack.config.js添加内容

### sass-loader : [github教程](https://github.com/webpack-contrib/sass-loader)
需要向webpack.config.js添加内容

### npm style-loader

### npm css-loader

#### webpack.config.js 文件中因为报错注释了几行代码：

	//  webpack.config.js全部内容（含注释的代码）：

	const path = require('path');

	module.exports = {
	    entry: './src/js/app.js',
	    output: {
	        filename: 'main.js',
	        path: path.resolve(__dirname, 'dist/js')
	    },
	    module: {
	        rules: [
	            {
	                test: /\.js$/,
	                exclude: /(node_modules|bower_components)/,
	                use: {
	                    loader: 'babel-loader',
	                    options: {
	                        presets: ['env']
	                    }
	                }
	            },
	            {
	                test: /\.scss$/,
	                use: [{
	                    loader: "style-loader"
	                }, {
	                    loader: "css-loader"
	                }, {
	                    loader: "sass-loader",
	                    // options: {
	                    //     implementation: require("dart-sass"),
	                    //     fiber: Fiber
	                    // }
	                }]
	            }
	        ]
	    }
	
	};