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

### Async/ Await

Async/ Await 是一种基于 Promise 处理异步操作的**语法糖**, 能以更接近同步代码的方式来编写异步代码

`async` 关键字用于声明一个函数是异步的:

- 这个函数**总是**返回一个 Promise
- 如果返回值为非 Promise 对象, 会自动包装成一个 resolved 状态的 Promise
- 如果函数抛出错误, 会自动包装成一个 rejected 状态的 Promise

`await` 关键字用于等待一个 Promise 对象的结果:

- 只能在 `async` 函数中使用
- 会暂停当前 `async` 函数的执行, 直到 Promise 对象完成

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
  }, 5000);
});

async function getData() {
  console.log("开始获取数据...");

  try {
    const result = await promise;
    console.log("获取数据成功:", result);
  } catch (error) {
    console.error("获取数据失败:", error);
  } finally {
    console.log("获取数据完成!");
  }
}

getData();
```

#### 优点

- **代码清晰**: `await` 关键字让异步操作的顺序一目了然
- **线性流程**: 代码从上到下执行, 更符合我们对同步代码的习惯
- **错误处理**: 使用`try-catch`块来捕获错误, 比`.catch()`更直观
