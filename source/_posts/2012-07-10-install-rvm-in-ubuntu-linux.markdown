---
layout: post
title: "在 Ubuntu Linux 中安裝 RVM(Ruby Version Manager)"
date: 2012-07-10 21:17
comments: true
categories: ruby
---

安裝必要套件
``` sh
$ sudo apt-get install bison build-essential libssl-dev
```

安裝 RVM 環境
``` sh
$ curl -L https://get.rvm.io | bash -s stable
```

修改 zshrc 讓 zsh 操作 rvm 更方便
``` sh
[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm" # Load RVM function
plugins=(... rvm ...)
```
重新開啟 Terminal 讓 zshrc 生效

讓 rvm 列出可以安裝的 ruby 環境
``` sh
$ rvm list known
```

安裝 Ruby 1.9.3
``` sh
$ rvm install 1.9.3
$ ruby --version
ruby 1.9.3p194 (2012-04-20 revision 35410) [i686-linux]
```
