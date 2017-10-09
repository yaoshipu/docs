## 列出产品模板

#### 注意事项

- 需要`user`权限

#### 请求:

    GET /api/templates/products

##### 返回:

**Code:** `200`

**Content:**

```
[
  {
    "product_name": "mongo-rs",
    "revision": 3,
    "groups": [
      "mongo-rs"
    ],
    "create_time": 1505790914,
    "update_time": 1505791016,
    "update_by": "yaoshipu",
    "enabled": true
  }
]
```	
##### 参数说明:

详见`创建产品模版`

##### 错误信息:

**Code:** `6102`

**Content:** `{ "message" : "List Template Error", "code": "6102", "description": "error details"}`
