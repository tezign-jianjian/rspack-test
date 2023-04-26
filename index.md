logo

Search Docs

⌘K
指南
配置
API
博客

生态

关于

开始
介绍
快速上手
术语表
特性
语言支持
资源模块
Loader
Plugin
模块解析
DevServer
优化
生产优化
代码分割
Tree shaking
包分析
框架支持
React
SolidJS
Vue
兼容性
Loader 兼容
Plugin 兼容
迁移
从 Webpack 迁移
Webpack 配置兼容性
从 Create React App 迁移
Storybook 迁移到 Rspack
其他
FAQ
功能规划
加入我们
团队
版权声明
品牌指南
基准测试
Webpack 配置兼容性#
TIP
Rspack 目前并不支持所有 webpack 配置，且有些配置会影响构建产物，为了保证构建产物的正确性，Rspack 默认开启了对配置的严格校验，但也提供了宽松模式来方便进行渐进式迁移，你可以通过设置 RSPACK_CONFIG_VALIDATE 环境变量进行开启：


# 开启宽松校验模式，会打印错误的配置但不会抛出错误
RSPACK_CONFIG_VALIDATE=loose rspack build
# 开启宽松校验模式，不打印错误也不抛出错误
RSPACK_CONFIG_VALIDATE=loose-silent rspack build
对比 webpack 5.

🟩 : 支持

🟥 : 不支持

🟧 : 部分支持

Entry#
string 🟩

string[] 🟩

EntryObject 🟧

import: EntryItem 🟩
runtime?: string | false 🟩
...others 🟥
Function 🟥

Context 🟩#
Mode 🟩#
Output#
Others

Output.assetModuleFilename 🟧#
string 🟩
function 🟥
Output.filename 🟧#
string 🟩
function 🟥
Output.chunkFilename 🟧#
string 🟩
function 🟥
Output.cssFilename 🟧#
string 🟩
function 🟥
Output.cssChunkFilename 🟧#
string 🟩
function 🟥
Output.path 🟩#
string
Output.publicPath 🟧#
string 🟩
function 🟥
Output.strictModuleErrorHandling 🟩#
boolean
Output.[...others] 🟥#
Template strings 🟧#
Compilation-level 🟧#
[fullhash] 🟩
[hash] 🟥
Chunk-level 🟩#
[id] 🟩
[name] 🟩
[chunkhash] 🟩
[contenthash] 🟩
Module-level 🟧#
[id] 🟩
[moduleid] 🟥
[hash] 🟩
[modulehash] 🟥
[contenthash] 🟩
File-level 🟧#
[file] 🟥
[query] 🟩
[fragment] 🟥
[base] 🟥
[filebase] 🟥
[path] 🟩
[name] 🟩
[ext] 🟩
URL-level 🟥#
[url] 🟥
Module#
Module.generator 🟥#
Module.parser 🟧#
Rule#
Rule Condition 🟧#
string 🟩
RegExp 🟩
function 🟥
Rule.exclude 🟩#
Rule.include 🟩#
Rule.loaders 🟩#
推荐使用 Rule.use。

Rule.parse 🟩#
dataUrlCondition 🟩
Rule.generator 🟧#
filename 🟩
dataUrl 🟥
emit 🟥
publicPath 🟥
outputPath 🟥
Rule.resource 🟩#
Rule.resourceQuery 🟩#
Rule.sideEffects 🟩#
Rule.test 🟧#
string 🟩
RegExp 🟩
function 🟥
array 🟩
object 🟩
Rule.type 🟧#
asset/resource 🟩
asset/inline 🟩
asset/source 🟩
asset 🟩
Other types supported by Rspack:

javascript/auto
typescript
css
css/module
json
Rule.use 🟧#
useEntry 🟩
function 🟥
Rule.resolve 🟧#
Rule.[...others] 🟥#
Resolve#
Resolve.alias 🟩#
Resolve.aliasField 🟧#
类型差异:

webpack: string[]
Rspack: Boolean
Resolve.conditionNames 🟩#
Resolve.extensions 🟧#
默认值不同:

webpack: ['.js', '.json', '.wasm']
rspack: ['.tsx', '.jsx', '.ts', '.js', '.json']
Resolve.fallback 🟩#
Resolve.mainFields 🟩#
Resolve.mainFiles 🟩#
Resolve.modules 🟩#
Resolve.preferRelative 🟩#
Resolve.[...others] 🟥#
Optimization#
Optimization.moduleIds 🟧#
natural 🟥
named 🟩
deterministic 🟩
size 🟥
Optimization.minimize 🟩#
Optimization.minimizer 🟧 ???#
plugins[] 🟩
function 🟥
Optimization.removeAvailableModules 🟧#
默认值不同:

webpack: 仅 production 模式下为 true
rspack: 默认都为 true
Optimization.removeEmptyChunks 🟩#
Optimization.runtimeChunk 🟧#
object 🟥
string 🟥
boolean 🟩
Optimization.sideEffects 🟩#
Optimization.splitChunks 🟧#
默认值完全相同。

splitChunks.automaticNameDelimiter 🟩#
splitChunks.chunks 🟩#
splitChunks.maxAsyncRequests 🟩#
splitChunks.maxInitialRequests 🟩#
splitChunks.defaultSizeTypes 🟩#
splitChunks.minChunks 🟩#
splitChunks.hidePathInfo#
splitChunks.minSize 🟧#
number 🟩
object 🟥
splitChunks.minSizeReduction 🟧#
number 🟩
object 🟥
splitChunks.enforceSizeThreshold 🟩#
splitChunks.minRemainingSize 🟩#
splitChunks.layer 🟥#
splitChunks.maxSize 🟩#
splitChunks.maxAsyncSize 🟩#
splitChunks.maxInitialSize 🟩#
splitChunks.name 🟩#
splitChunks.usedExports 🟥#
splitChunks.cacheGroups 🟧#
Plugins#
请看：plugin-compat.

支持的插件 api : plugin-api

Loaders#
请查看 loader-compat。

DevServer 🟧#
// todo

Cache 🟥#
rspack 只支持设置为布尔值。

Devtool 🟩#
Target 🟧#
async-node[[X].Y] 🟥
electron[[X].Y]-main 🟥
electron[[X].Y]-renderer 🟥
electron[[X].Y]-preload 🟥
node[[X].Y] 🟧
node
node-webkit[[X].Y] 🟥
nwjs[[X].Y] 🟥
web 🟩
webworker 🟩
esX 🟩
browserslist 🟩
Watch and WatchOptions 🟧#
Watch 🟩#
WatchOptions.aggregateTimeout 🟥#
WatchOptions.ignored 🟩#
WatchOptions.poll 🟩#
WatchOptions.followSymlinks 🟥#
WatchOptions.stdin 🟥#
Externals 🟧#
string 🟩
object 🟩
function 🟥
RegExp 🟥
[] 🟥
ExternalsType 🟧#
commonjs 🟩
global 🟩
module 🟩
promise 🟥
self 🟩
script 🟥
this 🟩
var 🟩
window 🟩
rspack 额外支持的属性:

amd
amd-require
import
jsonp
node-commonjs
system
umd
umd2
Performance 🟥#
Node 🟧#
Node.global 🟩#
Node.__dirname 🟩#
Node.__filename 🟥#
Stats 🟧#
// todo

Experiments 🟥#
虽然都有 experiments 配置项，但两者的实验功能完全不同，所以不要在 rspack 中配置 webpack 的实验功能。

Previous Page
从 Webpack 迁移
Next page
从 Create React App 迁移
ON THIS PAGE
Entry
Context 🟩
Mode 🟩
Output
Output.assetModuleFilename 🟧
Output.filename 🟧
Output.chunkFilename 🟧
Output.cssFilename 🟧
Output.cssChunkFilename 🟧
Output.path 🟩
Output.publicPath 🟧
Output.strictModuleErrorHandling 🟩
Output.[...others] 🟥
Template strings 🟧
Compilation-level 🟧
Chunk-level 🟩
Module-level 🟧
File-level 🟧
URL-level 🟥
Module
Module.generator 🟥
Module.parser 🟧
Rule
Rule Condition 🟧
Rule.exclude 🟩
Rule.include 🟩
Rule.loaders 🟩
Rule.parse 🟩
Rule.generator 🟧
Rule.resource 🟩
Rule.resourceQuery 🟩
Rule.sideEffects 🟩
Rule.test 🟧
Rule.type 🟧
Rule.use 🟧
Rule.resolve 🟧
Rule.[...others] 🟥
Resolve
Resolve.alias 🟩
Resolve.aliasField 🟧
Resolve.conditionNames 🟩
Resolve.extensions 🟧
Resolve.fallback 🟩
Resolve.mainFields 🟩
Resolve.mainFiles 🟩
Resolve.modules 🟩
Resolve.preferRelative 🟩
Resolve.[...others] 🟥
Optimization
Optimization.moduleIds 🟧
Optimization.minimize 🟩
Optimization.minimizer 🟧 ???
Optimization.removeAvailableModules 🟧
Optimization.removeEmptyChunks 🟩
Optimization.runtimeChunk 🟧
Optimization.sideEffects 🟩
Optimization.splitChunks 🟧
splitChunks.automaticNameDelimiter 🟩
splitChunks.chunks 🟩
splitChunks.maxAsyncRequests 🟩
splitChunks.maxInitialRequests 🟩
splitChunks.defaultSizeTypes 🟩
splitChunks.minChunks 🟩
splitChunks.hidePathInfo
splitChunks.minSize 🟧
splitChunks.minSizeReduction 🟧
splitChunks.enforceSizeThreshold 🟩
splitChunks.minRemainingSize 🟩
splitChunks.layer 🟥
splitChunks.maxSize 🟩
splitChunks.maxAsyncSize 🟩
splitChunks.maxInitialSize 🟩
splitChunks.name 🟩
splitChunks.usedExports 🟥
splitChunks.cacheGroups 🟧
Plugins
Loaders
DevServer 🟧
Cache 🟥
Devtool 🟩
Target 🟧
Watch and WatchOptions 🟧
Watch 🟩
WatchOptions.aggregateTimeout 🟥
WatchOptions.ignored 🟩
WatchOptions.poll 🟩
WatchOptions.followSymlinks 🟥
WatchOptions.stdin 🟥
Externals 🟧
ExternalsType 🟧
Performance 🟥
Node 🟧
Node.global 🟩
Node.__dirname 🟩
Node.__filename 🟥
Stats 🟧
Experiments 🟥
