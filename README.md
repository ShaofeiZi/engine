
## 作用

导出 **开发** 以及 **构建** 工作流的调用方法提供给 CLI 等上层工具

## 安装

```
npm i engine --save
```

## 使用

#### 开始之前，需要重写某些 node_modules 模块，例如：

```js
const path = require('path');
const override = require('engine/override');

( async ( ) => {
    await override(
        // 项目 node_modules 的绝对路径
        path.resolve( __dirname, './node_modules' ),
        // 项目 node_modules_override 的绝对路径
        path.resolve( __dirname, './node_modules/engine/node_modules_override' ),
        // 是否 debug 模式
        true,
    )
} )( );
```

#### 调用

```js
// messager 工作流消息输出机制
// dev 启动 开发 的异步函数
// build 启动 构建 的异步函数
const { messager, dev, build } = require('engine');

dev( Config );
```

### config
[config](./Config.md)
## 许可

[MIT](./LICENSE)
