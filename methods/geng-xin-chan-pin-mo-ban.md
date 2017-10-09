## 更新产品模板

#### 注意事项

- 需要`admin`权限
- 产品模板依赖次序在`groups`里描述
- 产品模板依赖服务组,需要调用`创建服务组模板`预先创建

#### 请求

```
PUT /api/templates/products/:name
```

##### 请求参数

```
Content-Type: application/json
```

```json
{
  "product_name": "product-X",
  "groups": [
    "group-A", "group-B"
  ],
  "enabled": true
}
```

##### 参数说明

详见`创建产品模版`

##### 正常返回

```
200 OK
```

##### 错误信息

```json
{
  "code": "400",
  "message" : "invalid ProductTmpl json args",
  "description": "Bad Request"
}
```

```json
{
  "code":6101,
  "message":"Update Template Error",
  "description":"error details"
}
```
