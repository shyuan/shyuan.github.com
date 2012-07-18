---
layout: post
title: "透過 NVM 使用 Node.js"
date: 2012-07-10 21:06
comments: true
categories: [node.js, javascript]
---

第一次聽到 Node.js 這套 Server Side 的 Javascript 開發環境是在 2011 年的三四月份，利用 Chrome 瀏覽器高效能的 V8 Javascript engine，作為運作 Server Side 的核心。
如果你是熟悉 Java 的開發人員，可以將 Node.js 視為一個以 C++ 開發出來的 Javascript 的 Virtual Machine。
Node.js 能擁有極高效能，除了得力於 V8 Engine 之外，Javascript 本身的 Event Base 的開發模式相較於傳統 Server Side 的 Multi-Threading 能更快速地回應 Client 的要求。

如果作業系統是 M$ Windows/Apple Mac，Node.js 的官網有提供安裝套件可以直接安裝。

但因為 Node.js 在目前還是處於快速發展的階段，平均一至兩週會有小版本更新，每兩至三月會有一個主版本 Release ，寫這篇文章的時候，最新的版本是 0.8.2。

就因為版本快速的變化，常常會發生在舊版本正常運作的套件或程式，在升到新版後卻無法正常運作，所以才有了 NVM (Node Version Manager) 來管理 Node.js 的版本。

有了 NVM ，便可以同時安裝多個不同版本的 Node.js ，並且可以很快速的在不同版本之間進行切換。

下面就來介紹要如何安裝 Node.js

[nvm on GitHub]: https://github.com/creationix/nvm/ "creationix/nvm"

直接用 git 下載安裝
``` sh
$ git clone git://github.com/creationix/nvm.git ~/nvm
```

如果要直接啟用 nvm 可以直接 source 剛剛下載回來的 nvm.sh
``` sh
$ source ~/nvm/nvm.sh
```

讓每次登入時直接載入 NVM ，把以下的判斷加入 Shell 的 RC
``` sh
[[ -s $HOME/nvm ]] && source $HOME/nvm/nvm.sh
```

重新啟動一個 Terminal 驗證 NVM 是否能被自動載入
```
$ nvm help            

Node Version Manager

Usage:
     nvm help                    Show this message
     nvm install <version>       Download and install a <version>
     nvm uninstall <version>     Uninstall a version
     nvm use <version>           Modify PATH to use <version>
     nvm run <version> [<args>]  Run <version> with <args> as arguments
     nvm ls                      List installed versions
     nvm ls <version>            List versions matching a given description
     nvm deactivate              Undo effects of NVM on current shell
     nvm alias [<pattern>]       Show all aliases beginning with <pattern>
     nvm alias <name> <version>  Set an alias named <name> pointing to <version>
     nvm unalias <name>          Deletes the alias named <name>
     nvm copy-packages <version> Install global NPM packages contained in <version> to current version
					       
Example:
    nvm install v0.4.12         Install a specific version number
    nvm use 0.2                 Use the latest available 0.2.x release
    nvm run 0.4.12 myApp.js     Run myApp.js using node v0.4.12
    nvm alias default 0.4       Auto use the latest installed v0.4.x version
```

在 Ubuntu 中必須要先安裝 build-essential 及 libssl-dev 這兩個套件
``` sh
$ apt-get install build-essential libssl-dev
```

安裝 Node.js 0.8.2
``` sh
$ nvm install v0.8.2
...
$ nvm list
v0.8.2
current:    v0.8.2
```
只要 nvm list 後有看到 current: v0.8.2 就表示安裝成功了

在 zsh 中如果沒有設定 default alias 可能會有執行的問題
```
$ node alias default 0.8.2 
$ nvm list
v0.8.2
current:    v0.8.2
default -> 0.8.2 (-> v0.8.2)
```

安裝其他版本的 Node.js ，以 0.6.19 為例
``` sh
$ nvm install v0.6.19
...

$ nvm list
v0.6.19	v0.8.2
current:    v0.8.2
default -> 0.8.2 (-> v0.8.2)

$ node --version
v0.8.2

$ nvm use 0.6.19

$ nvm list
v0.6.19	v0.8.2
current:    v0.6.19
default -> 0.8.2 (-> v0.8.2)

$ node --version
v0.6.19
```
