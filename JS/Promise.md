# Promise

## Promise的含义
    从语法来说promise是一个对象,从它可以获取异步操作的消息
## Promise的特点
    promise有以下两大特点
    1.对象的状态不受外界影响
      promise对象代表一个异步操作,有三种状态:pending（进行中）、fulfilled（已成功）和rejected（已失败）
    2.一旦状态改变，就不会再变，任何时候都可以得到这个结果
      Promise对象的状态改变，只有两种可能：从pending变为fulfilled和从pending变为rejected
## Promise的缺点
    一旦创建就无法中途取消
    如果不设置回调函数，Promise内部抛出的错误，不会反应到外部
    当处于pending状态时，无法得知目前进展到哪一个阶段
## Promise的基本用法
#### es6规定,Promise对象是一个构造函数，用来生成Promise实例
#### Promise构造函数接受一个函数作为参数，该函数的两个参数分别是resolve和reject
#### Promise实例生成以后，可以用then方法分别指定resolved状态和rejected状态的回调函数。

### 只有异步操作的结果，可以决定当前是哪一种状态，任何其他操作都无法改变这个状态，这也是promise这个名字的由来——“承诺”；

### 在构造 Promise 的时候，构造函数内部的代码是立即执行的
