
-   问：网页的 head 标签里面，表示的是页面的配置，有什么配置？[[html/html]]
-   答：字符集、关键词、页面描述、页面标题、IE 适配、视口、iPhone 小图标等等。
![[Pasted image 20220305220506.png]]

---


https://github.com/qiu-deqing/FE-interview#http-method
# seo 注意
1. 合理的 title、description、keywords
2. 语义化的 HTML 代码，符合 W3C 规范
3. 重要内容 HTML 代码放在最前：搜索引擎抓取 HTML 顺序是从上到下，有的搜索引擎对抓取长度有限制，保证重要内容一定会被抓取
4. 重要内容不要用 js 输出：爬虫不会执行 js 获取内容
5.  少用 iframe：搜索引擎不会抓取 iframe 中的内容
6. 非装饰性图片必须加 alt
7.  提高网站速度：网站速度是搜索引擎排序的一个重要指标

#  会话跟踪的方法有哪些  hard
1.  cookie
2.  session
3.  url 重写
4.  隐藏 input
5.  ip 地址

#  `<img>` 的 `title` 和 `alt` 有什么区别
1.  `title`是[global attributes](http://www.w3.org/TR/html-markup/global-attributes.html#common.attrs.core)之一，用于为元素提供附加的 advisory information。通常当鼠标滑动到元素上的时候显示。
2.  `alt` 是 `<img>` 的特有属性，是图片内容的等价描述，用于图片无法加载时显示、读屏器阅读图片。可提图片高可访问性，除了纯装饰图片外都必须设置有意义的值，搜索引擎会重点分析。

# web 语义化, 有什么好处
有标签语义化, css 命名语义化
- 方便代码维护； 
-  减少让开发者之间的沟通成本； 
-  能让语音合成工具正确识别网页元素的用途，以便作出正确的反应；
-  有利于 SEO, 搜索引擎可以更好地理解页面

* M : 方便理解,  自己 , 搜索引擎, 团队, 盲人

# 什么是渐进增强
指在 web 设计时强调可访问性、语义化 HTML 标签、外部样式表和脚本。保证所有人都能访问页面的基本内容和功能同时为高级浏览器和高带宽用户提供更好的用户体验。

# HTTP 状态码及其含义
- 1XX：信息状态码
	- **100 Continue**：客户端应当继续发送请求。
	- **101 Switching Protocols**
- 2XX：成功状态码
- 3XX：重定向
- 4XX：客户端错误
- 5XX: 服务器错误