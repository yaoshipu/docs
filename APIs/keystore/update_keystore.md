## 更新服务配置项

#### 注意事项

- 需要`user`权限

#### 请求

```
PUT /api/keystore/:key
```

##### 请求参数

```json
{
    "namespace": "shared-namespace",
    "value": "value"
}
```

##### 参数说明

无

##### 正常返回

```
200 OK
```

##### 错误返回
