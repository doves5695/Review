# 什么是fetch
    fetch的功能与XMLHttpRequest基本相同, 但有三个主要的差异
    (1).fetch使用promise, 不使用回调函数,简化了写法
    (2).fetch采用模块化设计,API分散在多个对象上(Response对象 Request对象 Headers对象)
    (3).fetch通过数据流处理数据,可以分块读取,有利于提高网站性能表现,XMLHttpRequest对象不支持数据流, 所有数据必须放在缓存里, 不支持分块读取, 必须等待全部拿到后, 再一次性吐出来
    在用法上，fetch()接受一个 URL 字符串作为参数，默认向该网址发出 GET 请求，返回一个 Promise 对象
