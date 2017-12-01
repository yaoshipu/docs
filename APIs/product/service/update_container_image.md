## 更新容器镜像

#### 注意事项

- 需要`user`权限

#### 请求

```
POST /api/image
```

##### 请求参数

```json
{
  "product_name": "product",
  "group_name": "group",
  "service_name": "service",
  "container_name": "container_name",
  "image": "image_full_name"
}
```

##### 参数说明

|参数|描述|
|---|---|
|product_name|产品名称|
|group_name|服务组名称|
|service_name|服务名称|
|container_name|容器名称|
|image|镜像|

##### 正常返回

```
200 OK
```

##### 错误返回
