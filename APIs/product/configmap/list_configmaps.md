# 列出服务配置

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/products/:productName/groups/:groupName/services/:serviceName/configmaps
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
[
  {
    "name": "hello",
    "age": "6m",
    "labels": {
      "s-group": "memcached",
      "s-product": "memcached",
      "s-service": "memcached"
    },
    "data": {
      "test1": "val1"
    }
  }
]
```

##### 错误返回
