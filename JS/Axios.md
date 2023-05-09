# 什么是axios

## axios是一个基于Promise的 用于浏览器和nodejs的HTTP客户端.简单来讲就是ajax的封装
    特点:
        从浏览器中创建XMLHTTPRequest
        从node.js发出http请求
        支持PromiseAPI
        拦截请求和响应
        转换请求和响应数据   
        取消请求    
        自动转换JSON数据
        客户端支持防止CSRF/XSRF

## axios处理并发操作
    axios处理并非操作的方式是axios.all()请求
