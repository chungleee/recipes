# List of Recipes

## React setup from scratch

1.	Project structure
```
src
---index.js
package.json
```

2.	Setting up Webpack
```
npm i webpack webpack-cli
```

webpack.config.js
```
module.exports = {
	entry: './src/index.js',  --> entry file aka the file you want to bundle
	output: {
		path: path.resolve(__dirname, 'public'),
		filename: 'bundle.js'
	},
}
```

3.	Babel
```
npm i @babel/core @babel/preset-env @babel/preset-react babel-loader
```

.babelrc
```
{
	"presets": ["@babel/preset-env", "@babel/preset-react"]
}
```

webpack.config.js
```
...
module: {
		rules: [
			{
				test:/\.(js|jsx)$/,
				exclude: /node_modules/,
				use: {
					loader: "babel-loader"
				}
			}
		]
	}
```

4.	React
```
npm i react react-dom
```

5.	Bundling CSS
```
npm i css-loader style-loader
```

webpack.config.js
```
...
{
	test: /\.css$/,
	use: ['style-loader', 'css-loader']
}
```

6.	HTML plugin
```
npm i html-webpack-plugin
```

webpack.config.js
```
module: {
	...
},
plugins: [
		new HtmlWebpackPlugin({
			template: './src/index.html'
		})
]
```

6.	Webpack hot reloading
```
npm i webpack-dev-server
```

package.json
```
scripts: "webpack-dev-server --mode development --open --hot"
```