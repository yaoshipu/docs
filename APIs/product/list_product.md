## 列出产品

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/products
```

##### 请求参数

无

##### 参数说明

|参数|说明|
|---|---|
|groups|为服务组依赖, 外层数组为顺序执行，内层数组为并行执行|
|status|为总体运行状态, 状态集包括|
|Running|运行良好|
|Unstable|运行不稳定, 部分服务未正常运行|
|Error|内部错误|
  
##### 正常返回

```json
[
  {
    "product_name": "portal-v4",
    "groups": ["portal-v4", "kodo"],
    "status": "Running"
  }
]
```

##### 错误返回
