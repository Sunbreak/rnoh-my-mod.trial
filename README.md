# 如何运行

1. 运行前端debug server

```sh
$ cd example && npm i
$ npm start
```

# 如何新建

1. 新建前端工程

```sh
$ mkdir my-mod && cd my-mod
$ npx react-native@0.72.5 init MyModExample --version 0.72.5 --skip-install
$ mv MyModExample example && cd example
$ rm -rf android ios
```

2. 参考[环境搭建](https://gitee.com/openharmony-sig/ohos_react_native/blob/0.72.5-ohos-5.0-release/docs/%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA.md)配置前端工程

# 参考

自定义TurboModule的实现：
https://gitee.com/openharmony-sig/ohos_react_native/blob/0.72.5-ohos-5.0-release/docs/TurboModule.md