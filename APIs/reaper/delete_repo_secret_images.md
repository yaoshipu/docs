## 批量删除密钥镜像配置

#### 注意事项

- 需要`admin`权限
- 删除用户下面所有Git仓库指定密钥的images值, 如果找不到对应的密钥则忽略

#### 请求

```
DELETE /api/secrets/:name/images
```

##### 请求参数

```json
{
"iamges": "index.qiniu.com/spock/docker-client"
}
```

##### 参数说明

|参数|说明|
|---|---|
|name|密钥名称|

##### 正常返回

```
200 OK
```

##### 错误返回
