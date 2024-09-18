> 因为`react_native_openharmony-xxx.har`源码包体积140MB，需要使用Git LFS插件，参考[Installing Git Large File Storage](https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage)

# 如何运行

0. 设置端口转发

```sh
$ hdc rport tcp:8081 tcp:8081
```

1. 运行前端debug server

```sh
$ cd example && npm i
$ npm start
```

2. DevStudio运行客户端工程

# 如何新建

## 创建前端工程

1. 新建前端工程

```sh
$ mkdir my-mod && cd my-mod
$ npx react-native@0.72.5 init MyModExample --version 0.72.5 --skip-install
$ mv MyModExample example && cd example
$ rm -rf android ios
```

2. 参考[环境搭建](https://gitee.com/openharmony-sig/ohos_react_native/blob/0.72.5-ohos-5.0-release/docs/%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA.md)配置前端工程

3. 新建pack文件夹，新建`pack/package.json`和`pack/src/NativeMyMod.ts`文件

4. 打包`react-native-my-mod-0.1.0.tgz`

5. 前端example工程更新依赖`react-native-my-mod-0.1.0.tgz`，添加示例代码

```sh
$ cd pack && npm pack --pack-destination ..
```

## 创建客户端工程

1. 使用DevStudio新建Empty Ability工程MyApplication，移动到harmony
2. AppScope中bundleName改为`com.example.my_mod`，app_name改为`MyModExample`
3. 参考[环境搭建](https://gitee.com/openharmony-sig/ohos_react_native/blob/0.72.5-ohos-5.0-release/docs/%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA.md)配置客户端工程
4. 新建Static Library模块my_mod

5. 运行codegen生成TurboModule注册代码

```sh
$ cd example && npm run codgen
```

6. 配置my_mod模块依赖rnoh.har：修改my_mod的`oh_package.json5`，新增my_mod的`CMakeList.txt`

7. 新增MyMod的C++注册代码`MyModPackage.h`和ArkTS实现代码`MyModePackage.ts`、`MyModeModule.ts`

8. 配置entry模块的依赖my_mod模块：修改entry的`oh_package.json5`和entry的`CMakeList.txt`

# 参考

自定义TurboModule的实现：
https://gitee.com/openharmony-sig/ohos_react_native/blob/0.72.5-ohos-5.0-release/docs/TurboModule.md