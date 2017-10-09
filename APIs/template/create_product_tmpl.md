## 创建产品模板

#### 注意事项

- 需要`admin`权限
- 产品模板依赖次序在`groups`里描述
- 产品模板依赖服务组,需要调用`创建服务组模板`预先创建

#### 请求

```
POST /api/templates/products
```

##### 请求参数

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

| 参数 | 描述 |
|-----|------|
| product_name | 产品名称，全局唯一 |
| groups | 产品依赖服务组，服务组按配置的先后顺序启动 |
| enabled | 是否启用模版, 暂时没有使用 |

##### 正常返回

```
200 OK
```

##### 错误返回

```json
{
  "code": "400",
  "message" : "invalid ProductTmpl json args",
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





