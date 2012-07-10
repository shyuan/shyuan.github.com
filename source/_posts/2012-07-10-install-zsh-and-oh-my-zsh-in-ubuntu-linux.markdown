---
layout: post
title: "在 Ubuntu Linux 中安裝 zsh 及 oh-my-zsh"
date: 2012-07-10 21:17
comments: true
categories: [zsh,linux]
---

直接用 apt-get 安裝 zsh 套件
``` sh
$ apt-get install zsh
$ zsh --verison
zsh 4.3.17
```

從 GitHub 下載 oh-my-zsh 套件
``` sh
$ git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
```

如果本來沒有安裝 zsh 可以直接使用 oh-my-zsh 的範例 zshrc
``` sh
$ cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

看看有什麼 Theme 可以用
``` sh
$ ls ~/.oh-my-zsh/themes
```

編輯 ~/.zshrc 更換 zsh 的 theme 我自己喜歡用 candy
``` sh
ZSH_THEME="candy"
```

看看有什麼 Plugin 可以用
``` sh
$ ls ~/.oh-my-zsh/plugins
```

編輯 ~/.zshrc 啟用 Plugin
``` sh
plugins=(git git-flow debian grails rvm history-substring-search github gradle svn node npm zsh-syntax-highlighting sublime)
```


