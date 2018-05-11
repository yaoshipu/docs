## 获取服务模板diff

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/diff/products/:product/groups/:group/services/:service
```

##### 请求参数

无

##### 参数说明
  
##### 正常返回
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




##### 错误返回
