## 环境准备

在Windows下安装，用官网上的rustup直接默认安装即可。

安装完成之后，就有了《The Rust Programming Language》这本书的离线HTML版本，直接用命令打开：

rustup doc --book

还要会使用强大的包管理器：cargo

这个cargo好用的另人发指，建项目、编译、运行都用用它：

cargo new euler1

cd euler1

cargo build

cargo run

由于众所周知的原因，在国内访问rust官网有些慢，特别是你在build时需要从网站自动下载大量的依赖库时，会非常慢，最好换成国内的镜像服务器，中国科技大学就有这样的镜像服务器。修改办法是，找到Cargo安装的文件夹，编辑config文件，文件内容：

\[source.crates-io\]

registry = "https://github.com/rust-lang/crates.io-index"

replace-with = 'ustc'

\[source.ustc\]

registry = "git://mirrors.ustc.edu.cn/crates.io-index"

还有一个编码习惯检查的小工具：clippy，可以帮助你检查出来一些写得不太规范的地方，推荐使用。

安装：

rustup component add clippy

使用：

Cargo clippy

开发集成环境我推荐微软的vscode，安装rust相关的插件rls，为了将来的调试，还要安装C/C++支持。

![](C:/Users/ccc/rustbook/.gitbook/assets/1.png)

调试程序的时候，首先打开vscode里的debug设置选项。

![](C:/Users/ccc/rustbook/.gitbook/assets/2.png)

再打开菜单Debug -&gt; Add Configuration，平台选C/C++ \(Windows\)，此时需要编辑launch.json里的“program”属性，例如：

"program": "${workspaceFolder}/target/debug/my\_program.exe”,

![](C:/Users/ccc/rustbook/.gitbook/assets/3.png)