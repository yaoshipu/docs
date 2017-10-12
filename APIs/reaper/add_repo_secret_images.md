## 批量添加密钥镜像配置

#### 注意事项

- 需要`admin`权限
- 添加用户下面所有 Repos 的 Secret Images, 如果找不到对应的 secret 则忽略

#### 请求

```
PUT /api/secrets/:name/images
```

##### 请求参数

```json
{
  "images": ["index.qiniu.com/spock/docker-client", "index.qiniu.com/spock/golang:1.7"]
}
```

##### 参数说明


##### 正常返回

```
200 OK
```

##### 错误返回
