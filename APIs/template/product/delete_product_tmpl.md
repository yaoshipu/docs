## 删除产品模板

#### 注意事项

- 需要`admin`权限

#### 请求

```
DELETE /api/templates/products/:name
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```
200 OK
```

##### 错误返回

```json
{
  "code":6104,
  "message":"Delete Template Error",
  "description":"error details"
}
```