## 创建配置模板

#### 注意事项

- 需要`admin`权限
- 配置模板需要指定`服务模板`
- 配置和服务名称以及渲染键规则: 
  ```
  [a-zA-Z_0-9$-]+
  ```
- 
#### 请求

```
POST /api/templates/configs
```

##### 请求参数

```json
{
  "config_name": "config1",
  "service_name": "svc1",
  "config_data": [
    {
      "key": "config_key",
      "value": "config_value"
    }
  ],
  "render_data": [
    {
      "name": "render_key1",
      "is_credential": false,
      "kv": [
        {
          "product": "KODO",
          "value": "render_value"
        }
      ]
    }
  ]
}
```

##### 参数说明

| 参数 | 描述 |
|-----|-----|
| config_name | 配置名称，用户唯一 |
| service_name | 配置属于的服务 |
| config_data | 配置内容 |
| render_data | 渲染键值内容 |

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
