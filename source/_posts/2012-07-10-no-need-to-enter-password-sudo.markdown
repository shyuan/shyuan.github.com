---
layout: post
title: "讓 sudo 不用輸入密碼"
date: 2012-07-10 15:36
comments: true
categories: linux
---

對於 sudo 常常問密碼感到麻煩嗎？改一下 /etc/sudoers 設定檔吧！

``` plain 把你的帳號加到 /etc/group 中
sudo:x:27:myAccount
```

``` plain 把 NOPASSWD: 加到 /etc/sudoers 的 sudo group 段落
# Allow members of group sudo to execute any command
%sudo   ALL=(ALL:ALL) NOPASSWD: ALL
```
