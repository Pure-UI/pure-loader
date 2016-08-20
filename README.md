# pure-loader [![npm package](https://img.shields.io/npm/v/pure-loader.svg?style=flat-square)](https://www.npmjs.org/package/pure-loader)

> webpack loader for [pure](https://github.com/fengzilong/pure)

## Installation

```bash
$ npm i pure-loader
```

## Usage

webpack.config.js

```js
var ExtractTextPlugin = require( 'extract-text-webpack-plugin' );

module.exports = {
	// ...
	entry: './index.js',
	module: {
		loaders: [
			{
				test: /\.rgl$/,
				loader: 'pure'
			}
		]
	},
	pure: {
		loaders: {
			css: ExtractTextPlugin.extract( 'css' ),
			mcss: ExtractTextPlugin.extract( 'css!mcss' )
		}
	},
	plugins: [
		// ...
		new ExtractTextPlugin( 'app.css' )
	]
};
```

app.rgl

```html
<style>
	html {
		background-color: #F2F2F2;
	}
</style>

<style lang="mcss" scoped>
	.outter {
		.inner {
			color: #000;
		}
	}
</style>

<template>
	<div class="outter">
		<div class="inner">RegularJs is Awesome <Button text="get started"></Button></div>
	</div>
</template>

<script>
	import Button from './button.rgl';

	// export options here
	export default {
		// shorthand for registering components in current component scope
		components: {
			'Button': Button,
		}
	}
</script>
```

Try it out!

## Related

- [regularjs](https://github.com/regularjs/regular)

## Thanks

- [vue-loader](https://github.com/vuejs/vue-loader)
