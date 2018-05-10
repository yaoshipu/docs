## 获取配置模板模板diff

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/diff/product/:product/group/:group/service/:service/config/:config
```

##### 请求参数

无

##### 参数说明
  
##### 正常返回
```json
  {
    "current": {
        "data": {
           "key": "a_config",
           "value": "b_value"
        }   
    },
    "latest": {
         "data": {
           "key": "a_config",
           "value": "b_value"
        }
    }
  }
```




##### 错误返回
