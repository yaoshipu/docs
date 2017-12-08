## 获取配置模板

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/templates/configs/:name/services/:service/revisions/:revision
```

##### 请求参数

无

##### 参数说明

| 参数 | 描述 |
|-----|-----|
| name | 配置名称 |
| service | 配置属于的服务 |
| revision | 版本号 |

##### 正常返回

```json
{
  "config_name": "test2",
  "service_name": "svc2",
  "revision": 1,
  "create_time": 1511877696,
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
```

##### 错误返回

```json
{
  "code":6100,
  "message":"Get Template Error",
  "description":"error details"
}
```
