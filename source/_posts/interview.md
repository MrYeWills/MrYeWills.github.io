---
title: 面试笔记
date: {{ date }}
tags: [typescript]
categories: 
- typescript
series: typescript
---
## webpack
### 基础
#### entry
#### output
#### loader
#### plugin
#### babel
### 开发阶段优化
#### dllplugin 第三方包缓存
[参考](http://www.ddpool.cn/article/42654.html)
#### css sourcemap根据需要打开
#### 路由的层面做懒加载react-loadable
#### 热重载与热替换

### 生产阶段优化
#### 长期资源通过hash值做缓存
静态文件缓存方案：这个最常看到。现在流行的方式是文件hash+强缓存的一个方案。比如hash+ cache control: max-age=1年。
#### 代码压缩
#### 减少http请求（图片的base64）
### 首屏优化
[这篇文章讲得好](https://juejin.im/post/6844904009581461518)
- 服务端渲染ssr next.js
- 服务器端进行gzip 传输文件压缩
- 组建按需加载
- cdn分发
通过在多台服务器部署相同的副本，当用户访问时，服务器根据用户跟哪台服务器地理距离小或者哪台服务器此时的压力小，来决定哪台服务器去响应这个请求。
- 缓存
## 其他
### http2与http1区别
- 二进制传输
http2采用二级制传输，相对于http1的文本传输安全性要高
- 多路复用
http一个链接只能提交一个请求，而http2能同时处理无数个请求，可以降低连接的数量，提高网络的吞吐量。
- 头部压缩
http2通过gzip与compress对头部进行压缩，并且在客户端与服务端各维护了一份头部索引表，只需要根据索引id就可以进行头部信息的传输，缩小了头部容量，间接提升了传输效率。
- 服务端推送
http2可以主动推送资源到客户端，避免客户端花过多时间逐个请求，降低相应时间
















