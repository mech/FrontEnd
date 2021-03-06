# Webpack

* [Awesome Webpack](https://github.com/d3viant0ne/awesome-webpack)
* [Deploying your React app to Heroku with Webpack](http://ditrospecta.com/javascript/react/es6/webpack/heroku/2015/08/08/deploying-react-webpack-heroku.html)
* [Long-term caching of static assets with Webpack](https://medium.com/@okonetchnikov/long-term-caching-of-static-assets-with-webpack-1ecb139adb95#.ts6yzv1s7)

[webpack-stats-plugin](https://github.com/FormidableLabs/webpack-stats-plugin)

## Webpack 2

- No need for empty string for `resolve.extensions`
- Must specify `-loader` at the end of all loaders.

---

* [Webpack 2 new documentation site](https://webpack.js.org/concepts/)
* [Code split component](https://github.com/ctrlplusb/code-split-component)
* [Webpack 2 Tree Shaking Configuration](http://moduscreate.com/webpack-2-tree-shaking-configuration/)
* [Code Splitting for React Router with ES6 Imports](http://moduscreate.com/code-splitting-for-react-router-with-es6-imports/)
* [Getting Started with Webpack 2](https://blog.madewithenvy.com/getting-started-with-webpack-2-ed2b86c68783#.2kd1zhnr3)
* [Webpack & HTTP/2](https://medium.com/webpack/webpack-http-2-7083ec3f3ce6#.e5uya9o19)
* [What's new in Webpack 2](https://gist.github.com/sokra/27b24881210b56bbaff7)
* [Migrating to Webpack 2](http://javascriptplayground.com/blog/2016/10/moving-to-webpack-2/)

---

- https://github.com/postcss/postcss-loader/issues/111
- https://github.com/webpack/webpack/issues/2557
- https://github.com/gaearon/redux-devtools/blob/master/examples/todomvc/index.js
- https://github.com/gaearon/react-hot-boilerplate/pull/61
- https://github.com/mhaagens/react-mobx-react-router4-boilerplate/blob/master/src/index.js
- https://github.com/ctrlplusb/code-split-component

## Loaders

Loaders preprocess files before Webpack bundles them.

* [See v2.1.0 beta.23 on `rules` replacing `loaders`](https://github.com/webpack/webpack/releases/tag/v2.1.0-beta.23)

## Hot Reloading - HMR, HSR, RHL

HMR is very delicate and hard to get right.

HMR is from Webpack utilising WebSocket and JSONP. style-loader gives you the ability to hot reload CSS. react-hot-loader is another one.

* [Hot State Reloading](https://medium.com/@tannerlinsley/introducing-hsr-the-hot-state-reloader-behind-jumpsuit-js-42498712ac90#.kn14mbsmc)
* [Webpack & The Hot Module Replacement](https://medium.com/@rajaraodv/webpack-hot-module-replacement-hmr-e756a726a07#.igxh3h3e5)
* [React Hot Loader 3.0](https://github.com/gaearon/react-hot-boilerplate/pull/61)

`react-hot-loader/babel` detects un-exported components.

You will get: `Warning: [react-router] You cannot change <Router routes>; it will be ignored`, please see [issues#2182](https://github.com/ReactTraining/react-router/issues/2182), but seems to be non issues with RR v4.

## Plugins

* DedupePlugin - **Deprecated!** Search for similar files and deduplicate them in the output.
* OccurrenceOrderPlugin - **No longer needed.** Module and chunk ID ordering. Ids that are used often get lower, shorter ID. This make things predictable and reduce total file size.
* [offline-plugin](https://github.com/NekR/offline-plugin)
* [inline-manifest-webpack-plugin](https://github.com/szrenwei/inline-manifest-webpack-plugin)
* [html-webpack-plugin](http://javascriptplayground.com/blog/2016/07/webpack-html-plugin/)

## Options

* chunkFilename - non-entry file, typically asynchronous split module like require.ensure.
* [UglifyJS2 compressor options](https://github.com/mishoo/UglifyJS2#compressor-options)

## Code Splitting

* [Code splitting with Webpack & React Router](https://brotzky.co/blog/code-splitting-react-router-webpack-2/)
* [Example of how to code split with Webpack 2 and React Router](https://github.com/brotzky/code-splitting)

---

* Commons Chunk - Extract out common code libraries into vendor
* Code splitting - Lazy loading of chunks of code as pages are visited.
* DLL - build times and caching

## Performance

Webpack and Browserify both underperform compared to Rollup and Closure Compiler, and the gap widens the more modules you add.

* [The cost of small modules](https://nolanlawson.com/2016/08/15/the-cost-of-small-modules/)
* [The cost of transpiling ES2015 in 2016](https://github.com/samccone/The-cost-of-transpiling-es2015-in-2016)