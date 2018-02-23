## 删除仓库 web hook

#### 注意事项

- 需要`admin`权限

#### 请求

```
POST /api/repos/:owner/:repo/hooks/delete
```

##### 请求参数

```json
{
  "ids": [123,345]
}
```

##### 正常返回

200 OK

##### 错误返回
