# flow-bin-loader
> [webpack](https://webpack.github.io/) loader for [Flow](https://flowtype.org/)

Built around [flow-bin](https://www.npmjs.com/package/flow-bin) to automate
type checking with [Flow](https://flowtype.org/).

## Install

```{.sh}
$ npm install --save-dev flow-bin flow-bin-loader
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

## Configuration

By default, modules are resolved with respect to the directory where 
`.flowconfig` lives, so you might need to tell Flow how to map paths to the 
correct directory.

In order to do that, create a file named `.flowconfig` in the root directory 
of your project and add

```
[options]
module.name_mapper='^\(.*\)$' -> '<PROJECT_ROOT>/path/to/root/\1'
```

where `path/to/root/` points to the same directory set in 
[`resolve.root`](https://webpack.github.io/docs/configuration.html#resolve-root).

For the complete list of options, please visit 
https://flowtype.org/docs/advanced-configuration.html
