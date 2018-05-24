## 列出产品

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/products
```

##### 请求参数

|参数|说明|
|---|---|
|active|默认不填为获取该用户全部产品，true为获取全部用户creating,updating,deleting产品|
|auth|默认不填为获取该用户全部产品，true为获取全部授权产品|

##### 参数说明

|参数|说明|
|---|---|
|groups|为服务组依赖, 外层数组为顺序执行，内层数组为并行执行|
|status|为总体运行状态, 状态集包括|
|Running|运行良好|
|Unstable|运行不稳定, 部分服务未正常运行|
|Error|内部错误|
  
##### 正常返回

查询当前用户产品
```json
[
  {
    "product_name": "portal-v4",
    "groups": ["portal-v4", "kodo"],
    "status": "Running",
    "owner": "yaoshipu"
  }
]
```

查询全部用户创建中，更新中，删除中产品
```json
[
  {
    "product_name": "portal-v4",
    "status": "Creating",
    "create_time": 1518084121,
    "update_time": 1518084121,
    "revision": 2,
    "update_by": "yaoshipu"
  }
]
```



##### 错误返回
