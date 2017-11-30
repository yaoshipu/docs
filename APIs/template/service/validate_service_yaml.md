## 检查服务模板Yaml

#### 注意事项

- 需要`user`权限

#### 请求

```
POST /api/templates/validate
```

##### 请求参数

```json
{
  "service_name": "svc1",
  "yamls": ["parsed yaml 1", "parsed yaml 2"]
}
```

##### 参数说明

无

##### 正常返回


##### 错误返回
