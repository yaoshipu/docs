## 删除配置模板

#### 注意事项

- 需要`user`权限
- 删除指定配置模板所有的版本号

#### 请求

```
GET /api/templates/configs/:name/services/:service
```

##### 请求参数

无

##### 参数说明

| 参数 | 描述 |
|-----|-----|
| name | 配置名称 |
| service | 配置属于的服务 |

##### 正常返回

```
200 OK
```

##### 错误返回

```json
{
  "code":6100,
  "message":"Delete Template Error",
  "description":"error details"
}
```
