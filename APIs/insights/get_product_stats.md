## 获取产品统计信息

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/insights/product
```

##### 请求参数

无

##### 参数说明

|参数|描述|
|---|---|
|products_count|总共有多少正在运行的产品|
|product_count|对应产品正在运行的个数|




##### 正常返回

```json
{
    "products_count": 5,
    "product_events": [
        {
            "product_name": "portal-v4",
            "product_count": 0,
            "create_duration": [
                {
                    "event": "CreateProduct",
                    "duration": 118
                }
            ],
            "update_duration": [
                {
                    "event": "UpdateProduct",
                    "duration": 1
                }
            ],
            "delete_duration": [
                {
                    "event": "DeleteProduct",
                    "duration": 63
                }
            ]
        }
    ]
```

##### 错误返回
