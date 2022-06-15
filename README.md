# MonkeyCrawler
A TamperMonkey (or other compatible monkeys) based demo crawler script.
一个基于油猴或其它猴类的爬虫演示脚本。

## 简介
爬取懂车帝的热门车型参数。  

## 使用方法
在GreasyFork上安装即可。

## 技术说明
本脚本主要尝试一种基于油猴脚本管理器的爬虫编写方法，脚本中采用了较为现代的编程技术，包括：
* 在页面上动态添加按钮启动爬取，且可以显示爬取进度；
* 不使用打开页面、定位DOM元素、模拟点击等传统浏览器自动化思路，而是由用户自己打开目标页面解决登录等问题后，在页面内直接连续发起多次异步请求；
* 直接使用浏览器原生 fetch 函数，不使用XMLHttpRequest等老式方法，也不依赖 JQuery, axios 等第三方库；
* 直接使用浏览器原生 querySelector(All) 函数，不依赖 JQuery；
* 对HTML文档也使用 fetch 函数请求，并使用原生 DOMParser 进行解析，使用 CSS 选择器获取数据；
* 前端页面为WebPack动态构建，元素类名不固定，使用`div[class^=xxx]`方式进行前缀匹配；
* 大量使用 async/await 语法实现异步请求；
* 使用 for await ... of 语法实现异步循环；
* 使用URL Blob 在浏览器端动态构建文件下载，不受 DataURL 长度限制；