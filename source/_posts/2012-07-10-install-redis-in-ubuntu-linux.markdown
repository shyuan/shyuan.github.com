---
layout: post
title: "在 Ubuntu Linux 中安裝 redis-server"
date: 2012-07-10 12:38
comments: true
categories: [service, redis]
---

由於在 Ubuntu 中預設套件庫中的 redis-server 版本過於老舊，所以我們透過非官方的 PPA 套件庫來安裝。
``` sh 從 Chris Lea 的 PPA 安裝 redis-server
$ sudo add-apt-repository ppa:chris-lea/redis-server
$ sudo apt-get update
$ sudo apt-get install redis-server
```

redis 有提供 CLI 指令進行操作，我們可以利用該指令實驗是否安裝成功
``` sh 測試 redis-server 是否安裝成功
$ redis-cli
redis 127.0.0.1:6379> INFO
redis_version:2.4.15
...
...
```
