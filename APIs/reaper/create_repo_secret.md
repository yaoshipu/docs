## 批量创建密钥配置

#### 注意事项

- 需要`admin`权限

#### 请求

```
POST /api/secrets
```

##### 请求参数

```json
{
  "name": "test-secret",
  "value": "test-pwd",
  "image": [
    "index.qiniu.com/spock/docker-client",
    "index.qiniu.com/spock/golang:1.7"
  ]
}
```

##### 参数说明


##### 正常返回

```
200 OK
```

##### 错误返回
