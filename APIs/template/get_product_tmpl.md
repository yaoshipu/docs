## 获取产品模板

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/templates/products/:name
```

##### 请求参数

##### 参数说明

详见`创建产品模版`

##### 正常返回

```json
{
  "product_name": "mongo-rs",
  "revision": 3,
  "groups": [
    {
      "group_name": "mongo-rs",
      "revision": 3,
      "create_time": 1505790878,
      "update_time": 1505803134,
      "update_by": "yaoshipu",
      "services": [
        [
          {
            "service_name": "mongo3.2",
            "revision": 7,
            "create_time": 1505803605,
            "create_by": "yaoshipu",
            "containers": [
              {
                "name": "mongo",
                "image": "mongo:3.2"
              }
            ]
          }
        ],
        [
          {
            "service_name": "mongo-init-job",
            "revision": 7,
            "create_time": 1505805892,
            "create_by": "yaoshipu",
            "containers": [
              {
                "name": "mongo-client",
                "image": "index.qiniu.com/spock/mongo-client"
              }
            ]
          }
        ]
      ]
    }
  ],
  "create_time": 1505790914,
  "update_time": 1505791016,
  "update_by": "yaoshipu",
  "enabled": true
}
```

##### 错误返回
