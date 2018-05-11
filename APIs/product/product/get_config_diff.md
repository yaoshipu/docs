## 获取配置模板模板diff

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/diff/products/:product/groups/:group/services/:service/configs/:config
```

##### 请求参数

无

##### 参数说明
  
##### 正常返回
```json
  {
    "current": {
        "data": [{
           "key": "a_config",
           "value": "b_value"
        }]   
    },
    "latest": {
         "data": [{
           "key": "a_config",
           "value": "b_value"
        }]
    }
  }
```




##### 错误返回
