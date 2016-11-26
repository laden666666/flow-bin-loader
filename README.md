# flow-bin-loader
> [webpack](https://webpack.github.io/) loader for [Flow](https://flowtype.org/)

Built around [`flow-bin`](https://www.npmjs.com/package/flow-bin) to automate
type checking with [Flow](https://flowtype.org/).

## Install

```{.sh}
$ npm install --save-dev flow-bin-loader
```
## Usage

In your webpack configuration

```{.js}
module.exports = {
  // ...
  module: {
    preLoaders: [
      // ...
      {
        test: /\.js$/,
        loader: 'flow-bin',
        exclude: /node_modules/,
      },
      // ...
    ]
  },
  // ...
}
```

Don't forget to add `// @flow` to the top of the files you want to be checked.

## Options

https://flowtype.org/docs/advanced-configuration.html

