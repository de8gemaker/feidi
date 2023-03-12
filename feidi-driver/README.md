# 飞滴-司机端

## 环境

node 16.15.1

## 运行

1、cd 到项目跟目录
2、安装依赖： npm install
3、运行 h5 端：npm run dev:h5

## 修改请求前缀（服务端地址）

### APP 或模拟器时

1、双击登录页的“飞滴出行，一路畅行” 进入设置页
2、点击首页的设置进入设置页

### 运行 h5 端时

1、找到根目录 vite.config.js

```js
    ...
  server: {
    proxy: {
      "/api": {
        // 你的服务端API接口
        target: "http://192.168.40.193:8088",
        changeOrigin: true,
        rewrite: (path) => path.replace(/^\/api/, "/")
      },
      "/sseApi": {
        // 你的SSE服务地址
        target: "http://192.168.40.193:60001",
        changeOrigin: true,
        rewrite: (path) => path.replace(/^\/sseApi/, "/")
      },
    },
  }
  ...

```
