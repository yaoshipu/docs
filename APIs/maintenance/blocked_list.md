## 查询维护状态

#### 注意事项

- 需要`super-admin`权限

#### 请求

```
GET /api/maintenance/blockedlist
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
[
  {
    "Method": "POST",
    "URL": "/api/v2/tasks"
  },
  {
    "Method": "POST",
    "URL": "/api/products"
  },
  {
    "Method": "DELETE",
    "URL": "/api/products"
  }
]
```

##### 错误返回
