# 如何运行

# 如何新建

1. 新建前端工程

```sh
$ mkdir my-mod && cd my-mod
$ npx react-native@0.72.5 init MyModExample --version 0.72.5 --skip-install
$ mv MyModExample example && cd example
$ rm -rf android ios
```

# 参考

自定义TurboModule的实现：
https://gitee.com/openharmony-sig/ohos_react_native/blob/0.72.5-ohos-5.0-release/docs/TurboModule.md