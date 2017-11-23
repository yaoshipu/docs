## 列出产品组模板

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/templates/groups
```

##### 请求参数

无

##### 参数说明

详见`创建服务组模版` 

##### 正常返回

```json
[
  {
    "group_name": "mongo-rs",
    "revision": 3,
    "create_time": 1505790878,
    "update_time": 1505803134,
    "update_by": "yaoshipu",
    "services": [
      [
        "mongo3.2"
      ],
      [
        "mongo-init-job"
      ]
    ]
  }
]
```	
##### 错误返回

```json
{
  "code": "6102",
  "message" : "List Template Error",
  "description": "error details"
}
```