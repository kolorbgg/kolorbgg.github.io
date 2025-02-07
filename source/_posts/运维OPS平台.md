---
layout: post
title: 运维OPS
date: 2025-02-07
tags: 
- 运维
categories:
- 运维
---
# 运维OPS平台

prometheus模块
k8s模块
cicd模块

cmdb，工单审批，任务执行grpc，服务树

系统用户

go语言要贴合项目，不然等于白学

最终目的：生产可用，不是demo。



**技能要求**

- 后端：go语言过关，写过一些脚本
- 前端：0基础，照着改vite
- 台式机：虚拟机Vmware

软件要求

- Golang 1.20 最新版
- Go ide: golang 
- Git for windows
- tortoise git
- 前端ide: webstorm
- 数据库工具：navicate
- 翻墙VPN

参考平台

- awesome-ops-system

  https://github.com/yjq635/awesome-ops-system



自己平台：

- 用户权限管理
  - 用户、角色、菜单三者的关系 多对多

- CICD

  - 可配置流水线，都有哪些步骤，哪些主机

  - 执行过程，可视化输出——柱状图
    - 执行到哪一步了，每一步的执行结果

  - 上线CD是需要工单的

- 资产管理
- 堡垒机-webssh
- 工单系统
  - 工单进度

- vue vben admin https://doc.vvbin.cn/

  https://github.com/vbenjs/vue-vben-admin





# 环境准备

## WebStrom和IDE





## 前端技术

**安装nvm和node.js**

安装内容：https://doc.vvbin.cn/guide/#%E5%AE%89%E8%A3%85

目录说明：https://doc.vvbin.cn/guide/#%E7%9B%AE%E5%BD%95%E8%AF%B4%E6%98%8E

- 推荐使用[pnpm](https://pnpm.io/)，否则依赖可能安装不上。
- [Node.js](http://nodejs.org/) 版本要求`14.x`以上，这里推荐 `20.x` 及以上。
- 推荐安装 [nvm](https://github.com/nvm-sh/nvm/tree/master) 来管理 `Node.js` 版本。

- node_mirror、nvm_mirror
- segmentfault.com/a/1190000020807954 

```
sudo npm install -g npm@11.0.0
sudo npm install -g pnpm
```



```
git clone https://github.com/vbenjs/vue-vben-admin.git

npm config set registry https://registry.npm.taobao.org --global

npm config set disturl https://npm.taobao.org/dist --global

# 出现相应npm版本即可
npm -v
# 出现相应node版本即可
node -v
# 全局安装pnpm
npm install -g pnpm
pnpm -v
# 安装依赖
pnpm i

pnpm run dev
```



测试环境变量

https://doc.vvbin.cn/guide/settings.html

.env文件：

```
# 测试
VITE_VAR_XIAOBIN = "小彬" 
```

App.vue

```
console.log("var:",import.meta.env.VITE_VAR_XIAOBIN);
```





![image-20250129132549957](运维OPS平台.assets/image-20250129132549957.png)



**vben菜单、路由、权限、mock、组件**

- https://doc.vvbin.cn/guide/router.html#%E9%85%8D%E7%BD%AE

- 在 [src/router/routes/modules](https://github.com/vbenjs/vue-vben-admin/tree/main/src/router/routes/modules) 内的 `.ts` 文件会被视为一个路由模块。

- 新建路由模块

  https://doc.vvbin.cn/guide/router.html#%E5%A6%82%E4%BD%95%E6%96%B0%E5%A2%9E%E4%B8%80%E4%B8%AA%E8%B7%AF%E7%94%B1%E6%A8%A1%E5%9D%97

  前端到50～97



## 后端技术

- 打印请求日志json_log
- 打印请求的body、header、requestId
- jwt认证
- 请求结构体校验
- Prometheus监控
- Casbin：权限管控







# 系统管理

- 后端控制的菜单

- json日志记录并滚动，可在阿里云SLS监控日志查看系统
