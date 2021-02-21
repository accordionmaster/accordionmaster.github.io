---
layout: post
title: "My JavaScript Notebook"
author: "Don Quixote"
tags: JavaScript
---

This is my JavaScript study notes. Although it is not systematic, I have accumulated a little bit in the learning process. I believe that one day, where I can't see and expect, it will come in handy.



## AJAX



```javascript
// 新建XMLHttpRequest对象
var request = new XMLHttpRequest();

// 状态发生变化时，函数被回调
request.onreadystatechange = function(){
	if (request.readyState === 4) {	// 成功完成
		// 判断响应结果
		if (request.status === 200) {
			// 成功，通过responseText拿到响应的文本
			return request.responseText;
		} else{
			return request.status;
		}
	} else{
		// HTTP请求还在继续
	}
}

request.open('GET', '/api/categories');
request.send();

alert('请求已发送，请等待响应');
```





<br>

_The end_
