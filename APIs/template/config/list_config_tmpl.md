## 获取配置模板

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/templates/configs
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```
[
  {
    "config": {
      "config_name": "test2",
      "service_name": "svc2"
    },
    "revision": 4
  },
  {
    "config": {
      "config_name": "test2",
      "service_name": "svc1"
    },
    "revision": 3
  },
  {
    "config": {
      "config_name": "test1",
      "service_name": "svc2"
    },
    "revision": 2
  },
  {
    "config": {
      "config_name": "test1",
      "service_name": "svc1"
    },
    "revision": 5
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
