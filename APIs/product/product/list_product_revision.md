## 列出产品更新信息

#### 注意事项

- 需要`user`权限

#### 请求

```
POST /api/revision/products
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
[
  {
    "product_name": "mongo-rs",
    "current_revision": 3,
    "next_revision": 3,
    "updatable": true,
    "groups_vevision": [
      {
        "group_name": "mongo-rs",
        "current_revision": 3,
        "next_revision": 3,
        "updatable": true,
        "services": [
          [
            {
              "service_name": "mongo3.2",
              "current_revision": 8,
              "next_revision": 8,
              "updatable": false
            }
          ],
          [
            {
              "service_name": "mongo-init-job",
              "current_revision": 8,
              "next_revision": 9,
              "updatable": true
            }
          ]
        ]
      }
    ]
  }
]
```

##### 错误返回
