# 什么是AJAX?
  Ajax是一种异步请求数据的web开发技术,对应改善用户的体验和页面性能有很大帮助.简单来说,在不重新刷新页面的情况下,Ajax通过异步请求加载后台数据,并在网页上呈现出来.
## ajax的目的: 
   提高用户体验,较少网络数据的传输量

## AJAX原理是什么
   Ajax相当于在用户和服务器之间加了一个中间层,使用户操作与服务器响应异步化.并不是所有的用户请求都提交给服务器，像一些数据验证和数据处理等都交给Ajax引擎自己来做，只有确定需要从服务器读取新数据时再由Ajax引擎向服务器提交请求。<br/>
   Ajax的原理简单来说通过[XmlHttpRequest]对象来向服务器发送异步请求，从服务器获得数据，然后用JavaScript来操作DOM而更新页面。这其中最关键的一步就是从服务器获得请求数据

## AJAX的使用
      var xhr = new XMLHttpRequest();
      // 注册一个事件，当ajax的状态改变的时候，就会触发
      xhr.onreadystatechange = function () {
         if (xhr.readyState === 4) { // 不论成功还是失败，只要结束就是 4
            let res = xhr.responseText;
         }
      }

      if (是GET请求) {
         xhr.open('请求方式', 'url?参数=值&参数=值');
            xhr.send();
      }

      if (是POST方式) {
         xhr.open('请求方式', 'url');
         xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
            xhr.send('参数=值&参数=值');
      }

## 服务器响应处理(区分同步跟异步两种情况)
   responseText 获得字符串形式的响应数据<br/>
   responseXML  获得XML形式的响应数据<br/>
   同步处理: 获取数据直接显示在页面上<br/>
   异步处理: 虽然相对复杂却比较推荐,但是要在请求状态改变事件中处理

## 什么是readyState?
### readyState是XMLHttpRequest对象的一个属性，用来标识当前XMLHttpRequest对象处于什么状态<br/>
### readyState总共有5个状态值，分别为0~4<br/>
      0:未初始化 — 尚未调用.open()方法；
      1:启动 — 已经调用.open()方法，但尚未调用.send()方法；
      2:发送 — 已经调用.send()方法，但尚未接收到响应；
      3:接收 — 已经接收到部分响应数据
      4:完成 — 已经接收到全部响应数据，而且已经可以在客户端使用了；

## 什么是status?
   HTTP状态码(status)由三个十进制数字组成，第一个十进制数字定义了状态码的类型，后两个数字没有分类的作用
