## 获取服务模板

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/templates/services/:name
```

##### 请求参数

reversion=1

##### 参数说明

| 参数 | 描述 |
|-----|------|
| service_name | 服务名称，全局唯一 |
| revision | 最新版本号 |
| yaml | 服务kube配置文件 |
| hash256 | yaml 文件内容 hash 值 |
| test | 配置测试服务额外字段 |

##### 正常返回

```json
{
  "service_name": "mongo3.2",
  "revision": 8,
  "yaml": "yaml content",
  "hash256": "84e1c479f679c7e04fc283482fdcecf81d1efce4f2e1bb478012a01d499a91c7",
  "create_time": 1505816729,
  "update_by": "yaoshipu",
  "containers": [
    {
      "name": "mongo",
      "image": "mongo:3.2"
    }
  ]
}
```

##### 错误返回
