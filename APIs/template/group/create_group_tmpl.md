## 创建产品组模板

#### 注意事项

- 需要`admin`权限
- 服务组模板依赖次序在`serviecs`里描述
- 服务组模板依赖服务,需要调用`创建服务模板`预先创建

#### 请求

```
POST /api/templates/groups
```

##### 请求参数

```json
{
  "group_name": "group-A",
  "services": [
    [
      "service-1",
      "service-2"
    ],
    [
      "service-3"
    ]
  ]
}
```

##### 参数说明

| 参数 | 描述 |
|-----|-----|
| group_name | 服务组名称，全局唯一 |
| services | 服务组依赖服务，服务按配置的先后顺序启动 |

##### 正常返回

```
200 OK
```

##### 错误返回

```json
{
  "code": "400",
  "message" : "invalid GroupTmpl json args",
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
