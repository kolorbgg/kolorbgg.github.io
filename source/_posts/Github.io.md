---
layout: post
title: 搭建Github.io
date: 2025-02-07
tags: 
- GitHub
categories:
- 通识
---
# 搭建Github.io
Github：https://xie.infoq.cn/article/ac51ce1f6e9434779c35cbb6c
```
https://hexo.io/zh-cn/
npm install hexo-cli -g
hexo init my-blog
cd my-blog
npm install
//
rm -rf node_modules package-lock.json
npm cache clean --force
npm install
//
hexo generate
hexo server
npm install --save hexo-theme-fluid
hexo new page about
/Users/kolor/my-blog/source/about/index.md
hexo new "My New Post"
~/blog/kolorbgg.github.io/source/_posts/My-New-Post.md
https://github.com/fluid-dev/hexo-theme-fluid

https://xie.infoq.cn/article/ac51ce1f6e9434779c35cbb6c


hexo new post my-blog-build-remark
设置文章的标题及其他元数据信息。
如上命令执行成功后，在 source/_posts/ 目录下生成了一个 Markdown 文件和一个同名的资源目录。

npm install hexo-deployer-git --save
hexo clean && hexo deploy
https://kolorbgg.github.io/


git config --global user.name "kolorbgg"
git config --global user.email "330289344@qq.com"
cat ~/.ssh/id_rsa.pub
ssh-add ~/.ssh/id_rsa
ssh -T git@github.com
```


在博客根路径下创建 _config.fluid.yml 文件，并将主题的 ./node_modules/hexo-theme-fluid/_config.yml 文件内容复制过去。
```
leancloud  统计网站 
web_analytics:  # 网页访问统计
  leancloud:
    app_id: F9X95HQHMyo84YlOYOdO5XdC-gzGzoHsz
    app_key: EfeFM6RKZa0s6ye1hoJr001q
    server_url: https://f9x95hqh.lc-cn-n1-shared.com
    ignore_local: true

footer:
  statistics:
    enable: true
    source: "leancloud"
    pv_format: "总访问量 {} 次"
    uv_format: "总访客数 {} 人"


post:
  meta:
    author: # 作者，优先根据 front-matter 里 author 字段，其次是 hexo 配置中 author 值
      enable: false
    date: # 文章日期，优先根据 front-matter 里 date 字段，其次是 md 文件日期
      enable: true
      format: "LL a" # 格式参照 ISO-8601 日期格式化 See: http://momentjs.cn/docs/#/parsing/string-format/
    wordcount: # 字数统计
      enable: true
      format: "{} 字"
    min2read: # 估计阅读全文需要的时长
      enable: true
      awl: 2
      wpm: 60
      format: "{} 分钟"
    views: # 浏览量计数
      enable: true
      source: "leancloud"
      format: "{} 次"


post:
  comments:
    enable: true
    type: valine

valine:
  appId: # LeanCloud AppID
  appKey: # LeanCloud AppKey
```
