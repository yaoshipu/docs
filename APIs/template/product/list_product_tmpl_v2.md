## 列出产品模板V2

#### 注意事项

* 需要`user`权限

#### 请求

```
GET /api/templates/products?max=1&start=1
```

##### 请求参数

|参数|说明|
|---|---|
|max|每页最大个数|
|start|第几个开始取|


##### 参数说明

详见`创建服务组模版`

##### 正常返回

```json

{
　　"data":[
　　　　{
　　　　　　"product_name":"portal-v4",
　　　　　　"revision":2,
　　　　　　"groups":[
　　　　　　　　"portal-v4"
　　　　　　],
　　　　　　"create_time":1509012086,
　　　　　　"update_time":1512454623,
　　　　　　"update_by":"guoyu",
　　　　　　"visibility":"public",
　　　　　　"enabled":true
　　　　}
　　],
　　"start_at":1,
　　"max_resault":1,
　　"total":21
}

```

##### 错误返回

```json
{
  "code": "6102",
  "message" : "List Template Error",
  "description": "error details"
}
```



