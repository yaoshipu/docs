## 创建配置模板

#### 注意事项

- 需要`admin`权限
- 配置模板需要指定`服务组模板`

#### 请求

```
POST /api/templates/configs
```

##### 请求参数

```json
{
  "config_name": "config1",
  "service_name": "svc1",
  "data": [
    {
      "key": "key1",
      "value": "value1"
    }
  ]
}
```

##### 参数说明

| 参数 | 描述 |
|-----|-----|
| config_name | 配置名称，用户唯一 |
| service_name | 配置属于的服务 |
| data | 配置内容 |

##### 正常返回

```
200 OK
```

##### 错误返回

```json
{
  "code": "400",
  "message" : "invalid ConfigTmpl json args",
  "description": "Bad Request"
}
```

```json
{
  "code":6100,
  "message":"Create Template Error",
  "description":"error details"
}
```
