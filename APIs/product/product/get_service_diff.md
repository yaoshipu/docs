## 获取服务模板diff

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/diff/product/:product/group/:group/service/:service
```

##### 请求参数

无

##### 参数说明
  
##### 正常返回

查询当前用户产品
```json
  {
    "current": {
        "yaml": "aaa",
        "update_by": "guoyu",
        "revision": 1
        
    },
    "latest": {
         "yaml": "aaa",
         "update_by": "guoyu",
         "revision": 1
    }
  }
```

查询全部用户创建中，更新中，删除中产品
```json
[
  {
    "product_name": "portal-v4",
    "status": "Creating",
    "create_time": 1518084121,
    "update_time": 1518084121,
    "revision": 2,
    "update_by": "yaoshipu"
  }
]
```



##### 错误返回
