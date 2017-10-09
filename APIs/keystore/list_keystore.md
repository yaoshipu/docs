## 列出服务配置项

#### 注意事项

- 需要`user`权限
- 普通用户只能列出自身服务配置项+共享服务配置
- 管理员用户可以列出全部服务配置项

#### 请求

```
GET /api/keystore
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
[
  {
    "namespace": "zhangdahe",
    "key": "ak",
    "value": "akvalue",
    "create_time": 1505045090,
    "update_time": 1505045090,
    "update_by": "zhangdahe"
  }
]
```

##### 错误返回
