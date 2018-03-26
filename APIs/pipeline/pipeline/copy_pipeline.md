## 复制Pipeline

#### 注意事项

- 需要admin权限

#### 请求

```
POST /api/v2/pipelines/old/:old/new/:new
```

##### 请求参数

无

##### 参数说明

| 参数 | 说明 |
| --- | --- |
| old | 被复制的pipeline名称 |
| new | 新创建的pipeline名称 |


##### 正常返回

```
200 OK
```

##### 错误返回
