### Promise

在 JavaScript 中，Promise 是一个用于处理异步操作的**对象**

#### Promise 的三种状态

一个 Promise 总是处于以下三种状态之一：

- **Pending (进行中)**: 初始状态, 表示异步操作正在进行中
- **Fulfilled (已成功)**: 表示异步操作成功完成, Promise 会返回一个值(value)
- **Rejected (已失败)**: 表示异步操作失败, Promise 会返回一个失败原因(reason)

#### 如何创建 Promise

Promise 对象通过 `new Promise()` 构造函数创建，接收一个包含异步操作的**函数**作为参数

这个函数有两个参数:

- `resolve`: 当异步操作成功时, 调用它并将结果作为参数传递
- `reject`: 当异步操作失败时, 调用它并将失败原因作为参数传递

#### 如何调用 Promise

Promise 对象主要有两个链式调用的方法, 用于处理异步操作的结果:

- `.then(onFulfilled)`: 当 Promise 成功时(Fulfilled), 执行这个函数
- `.catch(onRejected)`: 当 Promise 失败时(Rejected), 执行这个函数
- `.finally(onFinally)`: 无论 Promise 成功还是失败, 都会执行这个函数, 通常用于执行一些清理工作

#### 示例

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    const success = true;
    const data = "这是从服务器获取的数据";
    if (success) {
      resolve(data);
    } else {
      reject(new Error("网络请求失败!"));
    }
  }, 2000);
});

console.log("开始获取数据...");

promise
  .then((data) => {
    console.log("获取数据成功:", data);
  })
  .catch((error) => {
    console.log("获取数据失败:", error);
  })
  .finally(() => {
    console.log("获取数据完成!");
  });
```
