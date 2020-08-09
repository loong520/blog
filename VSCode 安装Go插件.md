# VSCode 安装Go插件

1. 在拓展中安装go插件

2. `Ctrl+Shift+P`打开命令，输入`Go:Install/Update Tools`，全选弹出框中的工具，安装时会出现如下错误：

   ​	Installing <font color=blue>github.com/mdempsky/gocode</font> FAILED

   ​	Installing <font color=blue>github.com/uudashr/gopkgs/v2/cmd/gopkgs</font> FAILED

   ​	Installing <font color=blue>github.com/ramya-rao-a/go-outline</font> FAILED

   ​	Installing <font color=blue>github.com/acroca/go-symbols</font> FAILED

   ​	Installing <font color=blue>golang.org/x/tools/cmd/guru</font> FAILED

   ​	Installing <font color=blue>golang.org/x/tools/cmd/gorename</font> FAILED

   ​	Installing <font color=blue>github.com/cweill/gotests</font> FAILED

   ​	Installing <font color=blue>github.com/fatih/gomodifytags</font> FAILED

   ​	Installing <font color=blue>github.com/josharian/impl</font> FAILED

   ​	Installing <font color=blue>github.com/davidrjenni/reftools/cmd/fillstruct</font> FAILED

   ​	Installing <font color=blue>github.com/haya14busa/goplay/cmd/goplay</font> FAILED

   ​	Installing <font color=blue>github.com/godoctor/godoctor</font> FAILED

   ​	Installing <font color=blue>github.com/go-delve/delve/cmd/dlv</font> FAILED

   ​	Installing <font color=blue>github.com/stamblerre/gocode</font> FAILED

   ​	Installing <font color=blue>github.com/rogpeppe/godef</font> FAILED

   ​	Installing <font color=blue>github.com/sqs/goreturns</font> FAILED

   ​	Installing <font color=blue>golang.org/x/lint/golint</font> FAILED
   
   **主要原因：**
       golang.org基于众所周知的原因无法直接访问，而go get在获取go code、go-def、golint等插件依赖工具的源码时，需要从golang.org上拉取部分代码至GOPATH

   **解决办法：**

   1. 进入`%GOPATH%\src`目录，创建`github.com`、`golang.org\x`目录

   2. 浏览器打开上面错误提示中的url地址，得到各自的git地址，进入`%GOPATH%\src\github.com`、`%GOPATH%\src\golang.org\x`，克隆各自的代码至本地目录：

      git clone git@github.com:fatih/gomodifytags.git

   3. 下载完所有源码之后，进行安装： 

   ​	   go install <font color=blue>github.com/mdempsky/gocode</font>

   ​	   go install <font color=blue>github.com/uudashr/gopkgs/v2/cmd/gopkgs</font>

   ​	   go install <font color=blue>github.com/ramya-rao-a/go-outline</font>

   ​	   go install <font color=blue>github.com/acroca/go-symbols</font>

   ​	   go install <font color=blue>golang.org/x/tools/cmd/guru</font>

   ​	   go install <font color=blue>golang.org/x/tools/cmd/gorename</font>

   ​	   go install <font color=blue>github.com/cweill/gotests</font>

   ​	   go install <font color=blue>github.com/fatih/gomodifytags</font>

   ​	   go install <font color=blue>github.com/josharian/impl</font>

   ​	   go install <font color=blue>github.com/davidrjenni/reftools/cmd/fillstruct</font>

   ​	   go install <font color=blue>github.com/haya14busa/goplay/cmd/goplay</font>

   ​	   go install <font color=blue>github.com/godoctor/godoctor</font>

   ​	   go install <font color=blue>github.com/go-delve/delve/cmd/dlv</font>

   ​	   go install <font color=blue>github.com/stamblerre/gocode</font>

   ​	   go install <font color=blue>github.com/rogpeppe/godef</font>

   ​	   go install <font color=blue>github.com/sqs/goreturns</font>

   ​	   go install <font color=blue>golang.org/x/lint/golint</font> 

   ​	  安装中可能还会确实一些源码包，根据提示下载依赖包
