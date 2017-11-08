## 查询服务容器

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/products/:productName/groups/:groupName/services/:serviceName/containers/:container
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

```
{
  "code": 6308,
  "description": "container memcached1 not found",
  "message": "get service pod error"
}
```