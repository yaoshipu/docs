## 列出产品模板

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/templates/products

```
##### 请求参数

无

##### 参数说明

详见`创建产品模版`

##### 正常返回

```json
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

##### 错误返回

```json
{
  "code": "6102",
  "message" : "List Template Error", 
  "description": "error details"
}
```
