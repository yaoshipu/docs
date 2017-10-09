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

```
Content-Type: application/json
```

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

##### 正常返回

##### 错误返回
