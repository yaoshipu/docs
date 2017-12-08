## 删除配置模板

#### 注意事项

- 需要`admin`权限
- 删除指定配置模板所有的版本号

#### 请求

```
DELETE /api/templates/configs/:old/new/:new/services/:service
```

##### 请求参数

无

##### 参数说明

| 参数 | 描述 |
|-----|-----|
| old | 旧配置名称 |
| new | 新配置名称 |
| service | 配置属于的服务 |

##### 正常返回

```
200 OK
```

##### 错误返回

```json
{
  "code":6100,
  "message":"Update Template Error",
  "description":"error details"
}
```
