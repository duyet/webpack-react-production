# Webpack React Production
Optimize Webpack + React + ES6 + Babel app production build file size

# How to config webpack React + ES6 + Babel in production

1. Update Source Maps
  ```js
  // webpack.config.js 
  devtool: 'cheap-module-source-map'
  ```

2. Node environment
  ```js
  plugins: [
   new webpack.DefinePlugin({
     'process.env': {
       'NODE_ENV': JSON.stringify('production')
     }
   })
  ],
  ```
3. Build prod w/ webpack 

  ```
  $> webpack --progress -p
  Hash: 39d00df29c750675828d
  Version: webpack 1.12.3
  Time: 4974ms
          Asset       Size  Chunks             Chunk Names
      bundle.js     131 kB       0  [emitted]  main
  bundle.js.map  156 bytes       0  [emitted]  main
      + 154 hidden modules
  ```

The new bundle is now 131 kB. It may not look as dramatic as the improvement we made in the previous step, but it’s still a phenomenal 30% decrease in size.

Just two simple configuration changes lead us to **82% savings** in the output size.

# How to contribute

1. Fork the project on Github
2. Create a topic branch for your changes
3. Ensure that you provide documentation and test coverage for your changes (patches won’t be accepted without)
4. Create a pull request on Github (these are also a great place to start a conversation around a patch as early as possible)

# License
MIT License

Copyright (c) 2015 Van-Duyet Le

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
