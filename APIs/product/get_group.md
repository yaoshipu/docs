## 查询服务组

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/products/:productName/groups/:groupName`
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
[
  {
    "service_name": "mongo-init-job",
    "pods": []
  },
  {
    "service_name": "mongo3.2",
    "pods": [
      {
        "name": "mongo-0",
        "ready": "1/1",
        "status": "Running",
        "restarts": 0,
        "age": "23h",
        "ip": "172.20.177.132",
        "node": "cs58"
      },
      {
        "name": "mongo-1",
        "ready": "1/1",
        "status": "Running",
        "restarts": 1,
        "age": "23h",
        "ip": "172.20.229.185",
        "node": "cs23"
      },
      {
        "name": "mongo-2",
        "ready": "1/1",
        "status": "Running",
        "restarts": 0,
        "age": "23h",
        "ip": "172.20.66.161",
        "node": "cs24"
      }
    ]
  }
]
```

##### 错误返回
