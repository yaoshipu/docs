# 创建服务配置

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/configmaps/:name
```

##### 请求参数

```
{
    "name": "apps-api-configmap",
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
