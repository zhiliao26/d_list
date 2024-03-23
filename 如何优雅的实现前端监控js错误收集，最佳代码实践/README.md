# 如何优雅的实现前端监控js错误收集，最佳代码实践

```javascript
// 使用 addEventListener error 来捕获 src资源加载错误 js运行错误
window.addEventListener('error', (e) => {
  console.log('addEventListener-error', e);
  return true;
},
  true // 利用捕获阶段处理
);

// 使用 addEventListener unhandledrejection 来捕获 异步promise错误
window.addEventListener('unhandledrejection', (e) => {
  throw e.reason; // 抛出异常 交予 addEventListener error 一同处理
});
```
