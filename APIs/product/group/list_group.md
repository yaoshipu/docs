## 列出服务组

#### 注意事项

- 需要`user`权限
- 产品状态有如下3种:
  - Successful: 运行良好
  - Unstable: 运行不稳定（部分stack/service挂了）
  - Failed: 创建失败
  
#### 请求

```
GET /api/products/:productName/groups
```

##### 请求参数

|参数|说明|
|---|---|
|productOwner|默认不填为获取该用户全部服务器，填 {owner name} 为获取被授权产品服务组信息|

##### 参数说明

无

##### 正常返回

```json
  [
    {
      "group_name": "portal-v4",
      "services": [
        [
          "index",
          "kirk",
          "kodo",
          "fusion"
        ]
      ],
      "status": "Running",
      "product_owner": "yaoshipu"
    }
  ]
```
##### 错误返回
