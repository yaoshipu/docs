## 获取配置模板

#### 注意事项

- 需要`user`权限
- 返回每个配置最新的版本

#### 请求

```
GET /api/templates/configs?service=svc1
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
[
  {
    "config_name": "test1",
    "service_name": "svc1",
    "revision": 1,
    "create_time": 1511877960,
    "create_by": "yaoshipu",
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
]
```

##### 错误返回

```json
{
  "code":6100,
  "message":"List Template Error",
  "description":"error details"
}
```
