# Webpack

* [Deploying your React app to Heroku with Webpack](http://ditrospecta.com/javascript/react/es6/webpack/heroku/2015/08/08/deploying-react-webpack-heroku.html)
* [Long-term caching of static assets with Webpack](https://medium.com/@okonetchnikov/long-term-caching-of-static-assets-with-webpack-1ecb139adb95#.ts6yzv1s7)

[webpack-stats-plugin](https://github.com/FormidableLabs/webpack-stats-plugin)

## Plugins

* DedupePlugin - Search for similar files and deduplicate them in the output.
* OccurrenceOrderPlugin - Module and chunk ID ordering. Ids that are used often get lower, shorter ID. This make things predictable and reduce total file size.

## Options

* chunkFilename - non-entry file, typically asynchronous split module like require.ensure.
* [UglifyJS2 compressor options](https://github.com/mishoo/UglifyJS2#compressor-options)

## Performance

Webpack and Browserify both underperform compared to Rollup and Closure Compiler, and the gap widens the more modules you add.

* [The cost of small modules](https://nolanlawson.com/2016/08/15/the-cost-of-small-modules/)
* [The cost of transpiling ES2015 in 2016](https://github.com/samccone/The-cost-of-transpiling-es2015-in-2016)