# Rust-Wasm官方小练习

本demo配套教材为官方wasm小册：https://rustwasm.github.io/docs/book/introduction.html

## 环境准备

1. 安装wasm-pack: `curl https://rustwasm.github.io/wasm-pack/installer/init.sh -sSf | sh`
2. 安装cargo-generate: `cargo install cargo-generate`
3. 安装npm: `npm install npm@latest -g`

## 本地启动

1. 进入play-wasm-bindgen目录，使用wasm-pack将rust编译成wasm`wasm-pack build --target web`
2. 进入www目录，运行`yarn serve`


## 说明

1. 官方配套教材有些老旧了，所以完全按照官方的抄，有可能会连编译都通过不了
2. 本demo实现了官方教程除了参考和bench基准测试之外的功能，包括：rust wasm构建/canvas交互/性能测试展示等
3. 本质上由rust构建出来的wasm属于独立的包，所以需要使用monorepo的思想去进行本项目的依赖按照，yarn serve已经帮你做好了
4. www目录是前端内容，相关的webpack配置需要自己写，比较简单，官方有个webpack的wasm打包插件，挺方便的，但是在我自己的本地用老是得不到我想要的那种效果（也许我不太会用）就删除改成手动pack wasm了
5. rust打出来的也发到npm上了，地址：https://www.npmjs.com/package/play-wasm-bindgen

## 唠叨

晚上搞项目有点头晕，遂花了点时间把这个demo做了，收益还是颇多的。最近开发紧张也抽不开时间写wasm相关的东东，不过也抽空搞了下wasm，尝试把自己项目的去背景用到的js漫水算法改成了wasm的形式，但是发现自己对rust生命周期的概念掌握的还不行，但是如果移动了imageData的所有权我就陷入了困境不知道咋搞。本来最近还发现floodfill在我自己项目中好像还能通过多线程加速计算，就找了一个crate叫做threadpool，有点思路但还是不太会搞，主要还是Mutex和Arc这些概念没真的掌握吧，任重道远～