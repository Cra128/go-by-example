### 安装 Go 语言

1. 访问 [go.dev/](https://link.juejin.cn/?target=https%3A%2F%2Fgo.dev%2F) ，点击 Download ，下载对应平台安装包，安装即可
2. 如果无法访问上述网址，可以改为访问 [studygolang.com/dl](https://link.juejin.cn/?target=https%3A%2F%2Fstudygolang.com%2Fdl) 下载安装
3. 如果访问 github 速度比较慢，建议配置 go mod proxy，参考 [goproxy.cn/](https://link.juejin.cn/?target=https%3A%2F%2Fgoproxy.cn%2F) 里面的描述配置，下载第三方依赖包的速度可以大大加快



### 修改GOPATH变量

- GOPATH是go的第三方库、go程序运行的目录

- 为了方便开发，实际上会设置多个GOPATH变量

- Mac的shell有多种解释器，不同的shell有不同的配置方式

  > ## shell有哪些？
  >
  > **1、zsh**
  > 很多人的 mac 中会使用 [zsh](https://so.csdn.net/so/search?q=zsh&spm=1001.2101.3001.7020) 而不是 bash，一大半是因为 oh-my-zsh 这个配置集，它兼容 bash，还有自动补全等好用的功能。
  > **2、sh**
  > sh的全称是 Bourne shell，由 AT&T 公司的 Steve Bourne开发，为了纪念他，就用他的名字命名了。sh 是 UNIX 上的标准 shell，很多 UNIX 版本都配有 sh。sh 是第一个流行的 shell。
  > **3、csh**
  > sh 之后另一个广为流传的 shell 是由柏克莱大学的 Bill Joy 设计的，这个 shell 的语法有点类似C语言，所以才得名为 C shell ，简称为 csh。
  > **4、tcsh**
  > tcsh 是 csh 的增强版，加入了命令补全功能，提供了更加强大的语法支持。
  > ash一个简单的轻量级的 Shell，占用资源少，适合运行于低内存环境，但是与下面讲到的 bash shell 完全兼容。
  > **5、bash**
  > bash由 GNU 组织开发，保持了对 sh shell 的兼容性，是各种 Linux 发行版默认配置的 shell。bash 兼容 sh 意味着，针对 sh 编写的 shell 代码可以不加修改地在 bash 中运行。尽管如此，bash 和 sh 还是有一些不同之处：一方面，bash 扩展了一些命令和参数；另一方面，bash 并不完全和 sh 兼容，它们有些行为并不一致，但在大多数企业运维的情况下区别不大，特殊场景可以使用 bash 代替 sh。

- 这里仅展示zsh的配置方式

  ```shell
  sudo vim ~/.bash_profile
  添加如下代码($HOME后边是具体的存放路径)：
  export GOPATH=$HOME/Code/GoCoding/goWorkSpace
  
  sudo vim ~/.zshrc
  添加如下代码：
  source ~/.bash_profile
  export PATH=$PATH:/usr/local/go/bin
  
  执行.zsh文件
  source ~/.zshrc
  ```

  

### 配置 Go 语言开发环境

- 后期想做Java，就选择了VScode

- 需要安装go插件

- 下载了go插件后，打开vs code 选择install - all安装go tools。安装的时候可能会报错：

  > Installing github.com/mdempsky/gocode FAILED
  > Installing github.com/uudashr/gopkgs/v2/cmd/gopkgs FAILED
  > Installing github.com/ramya-rao-a/go-outline FAILED
  > Installing github.com/acroca/go-symbols FAILED
  > Installing golang.org/x/tools/cmd/guru FAILED
  > Installing golang.org/x/tools/cmd/gorename FAILED
  > Installing github.com/cweill/gotests/… FAILED
  > Installing github.com/fatih/gomodifytags FAILED
  > Installing github.com/josharian/impl FAILED
  > Installing github.com/davidrjenni/reftools/cmd/fillstruct FAILED
  > Installing github.com/haya14busa/goplay/cmd/goplay FAILED
  > Installing github.com/godoctor/godoctor FAILED
  > Installing github.com/go-delve/delve/cmd/dlv FAILED
  > Installing github.com/stamblerre/gocode FAILED
  > Installing github.com/rogpeppe/godef FAILED
  > Installing github.com/sqs/goreturns FAILED
  > Installing golang.org/x/lint/golint FAILED

  **使用go mod 代理来安装**

  https://goproxy.io是一个国内的代理

  执行

  ```shell
  go env -w GO111MODULE=on
  go env -w GOPROXY=https://proxy.golang.com.cn,direct
  ```

  关闭vs code 再次执行安装即可。

  **系统提示安装Xcode ** 

  > xcode-select: note: no developer tools were found at ‘/Applications/Xcode.app‘, requesting install.

  可以打开https://developer.apple.com/download/more/ 

  下载Command Line Tools for Xcode即可。

### VSCode中git使用

- vscode 拉取git仓库

  直接选择克隆存储库，输入你的仓库地址，然后回车选择要存储的位置即可！

- vscode提交代码

  ```shell
  git add 
  git commit -m "注释信息"
  git push
  ```

  

​		