#速度分析
speed-measure-webpack-plugin
#体积分析
webpack-bundle-analyzer
#并行打包
happypack(作者已不维护) thread-loader(原生)
#并行压缩
terser-webpack-plugin, uglifyjs-webpack-plugin
#分包
DLLPlugin进行分包，DllReferencePlugin 对manifest.json 引用
#缓存
1.terser-webpack-plugin/uglifyjs-webpack-plugin cache: true
2.babel-loader?cacheDirectory=true
3.hard-source-webpack-plugin
#缩小构建
  alias,extensions,mainFields