Javascript 是⼀⻔单线程语⾔。早期我们解决异步场景时，⼤部分情况都是通过回调函数（把函数 A 传给另一个函数 B 调用，那么函数 A 就是回调函数）来进⾏。 
### Promise 的介绍
Promise 对象，可以**用同步的表现形式来书写异步代码**（也就是说，代码看起来是同步的，但本质上的运行过程是异步的）
```
// 伪代码1
myPromise()
    .then(
        function () {},
        function () {}
    )
    .then(
        function () {},
        function () {}
    )
    .then(
        function () {},
        function () {}
    );

// 伪代码2
是时候展现真正的厨艺了().然后(买菜).然后(做饭).然后(洗碗);
```
### 使用 Promise
（1）通过 `new Promise()` 构造出一个 Promise 实例。Promise 的构造函数中传入一个参数，这个参数是一个函数，该函数用于处理异步任务。

（2）函数中传入两个参数：resolve 和 reject，分别表示异步执行成功后的回调函数和异步执行失败后的回调函数。代表着我们需要改变当前实例的状态到**已完成**或是**已拒绝**。

（3）通过 promise.then () 和 promise.catch () 处理返回结果（这里的 `promise` 指的是 Promise 实例）。

### promise 对象的 3 个状态

-   初始化（等待中）：pending
    
-   成功：fulfilled
    
-   失败：rejected

```
// 创建 promise 实例
let promise = new Promise((resolve, reject) => {
    //进来之后，状态为pending
    console.log('同步代码'); //这行代码是同步的
    //开始执行异步操作（这里开始，写异步的代码，比如ajax请求 or 开启定时器）
    if (异步的ajax请求成功) {
        console.log('333');
        resolve('请求成功，并传参'); //如果请求成功了，请写resolve()，此时，promise的状态会被自动修改为fulfilled（成功状态）
    } else {
        reject('请求失败，并传参'); //如果请求失败了，请写reject()，此时，promise的状态会被自动修改为rejected（失败状态）
    }
});
console.log('222');

//调用promise的then()：开始处理成功和失败
promise.then(
    (successMsg) => {
        // 处理 promise 的成功状态：如果promise的状态为fulfilled，则执行这里的代码
        console.log(successMsg, '成功了'); // 这里的 successMsg 是前面的 resolve('请求成功，并传参')  传过来的参数
    },
    (errorMsg) => {
        //处理 promise 的失败状态：如果promise的状态为rejected，则执行这里的代码
        console.log(errorMsg, '失败了'); // 这里的 errorMsg 是前面的 reject('请求失败，并传参') 传过来的参数
    }
);
```

promise 封装  skim