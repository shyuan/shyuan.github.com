---
layout: post
title: "在 GitHub 上使用 git-flow"
date: 2012-08-09 19:26
comments: true
categories: 
---

Vincent Driessen 建立了一個還不錯的 Git 分支管理的工作模式 git-flow
[A successful Git branching model]: http://nvie.com/posts/a-successful-git-branching-model/

``` sh 在 Ubuntu 中安裝 git-flow
$ apt-get install git-flow
```

``` sh 初始化一個新的 Repository 並將其命名為 fakerepo
$ git init fakerepo
$ cd fakerepo
```

``` sh 在 Repository 中初始化 git-flow，git-flow 會問你要不要換 Branch 的名稱，這邊都 follow 預設名稱，一直按 Enter 就行了
$ git flow init
No branches exist yet. Base branches must be created now.
Branch name for production releases: [master] 
Branch name for "next release" development: [develop] 

How to name your supporting branch prefixes?
Feature branches? [feature/] 
Release branches? [release/] 
Hotfix branches? [hotfix/] 
Support branches? [support/] 
Version tag prefix? []
```

``` sh 檢查 Branch 是否都有被成功建立出來
$ git branch
* develop
  master
$ git config -l | grep gitflow
gitflow.branch.master=master
gitflow.branch.develop=develop
gitflow.prefix.feature=feature/
gitflow.prefix.release=release/
gitflow.prefix.hotfix=hotfix/
gitflow.prefix.support=support/
gitflow.prefix.versiontag=
```

``` sh 把剛建好的 Repository 送上 GitHub
$ git remote add origin https://github.com/shyuan/fakerepo.git
$ git push --set-upstream origin develop 
To https://github.com/shyuan/fakerepo.git
 * [new branch]      develop -> develop
Branch develop set up to track remote branch develop from origin.
$ git push --set-upstream origin master
To https://github.com/shyuan/fakerepo.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
```

``` sh 檢查 Branch
$ git branch
* develop
  master
$ git branch -r
  origin/develop
  origin/master
```

``` sh 其他使用者的操作步驟
$ git clone https://github.com/shyuan/fakerepo.git
$ cd fakerepo
$ git branch
* master
$ git branch -r
origin/HEAD -> origin/master
origin/develop
origin/master
$ git flow init
Which branch should be used for bringing forth production releases?
   - master
Branch name for production releases: [master] 
Branch name for "next release" development: [develop] 

How to name your supporting branch prefixes?
Feature branches? [feature/] 
Release branches? [release/] 
Hotfix branches? [hotfix/] 
Support branches? [support/] 
Version tag prefix? []
```
