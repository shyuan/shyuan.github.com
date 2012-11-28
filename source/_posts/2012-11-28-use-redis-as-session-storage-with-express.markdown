---
layout: post
title: "在 Express 下使用 Redis 來存 Session"
date: 2012-11-28 23:14
comments: true
categories: [redis, node.js]
---

# 加上 Dependent Package
在 package.json 中加入 "connect-redis"

# 修改 app.js
```
var RedisStore = require('connect-redis')(express);
var sessionStore = new RedisStore({ttl: 1800}); // ttl 是 Expire 的秒數

app.use(express.session({ key: 'abcde', secret: 'WoW LoL', store: sessionStore}));
```

預設會自動連 localhost 的 Redis

可參考 [express-redis-session](https://github.com/shyuan/express-redis-session)

 [visionmedia/connect-redis](https://github.com/visionmedia/connect-redis)
