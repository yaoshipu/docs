# 更新服务配置

#### 注意事项

- 需要`user`权限

#### 请求

```
POST /api/products/:productName/groups/:groupName/services/:serviceName/configmaps/:configName

```

##### 请求参数

```json
{
    "data": {
        "key": "value"
    }
}
```

##### 参数说明

无

##### 正常返回

```
200 OK
```

##### 错误返回
