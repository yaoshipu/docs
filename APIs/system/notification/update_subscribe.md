## 更新关注

#### 注意事项

- 需要`user`权限

#### 请求

```
PUT /api/notify/subscribe/:type"
```

##### 请求参数

```json
{
   "pipelinestatus":"passed"
}
```

##### 参数说明

|参数|描述|
|---|---|
|pipelinestatus|`passed`关注通过信息，`failed`关注失败信息，`*`关注所有信息(notify_type：2)|

##### 正常返回

```
200 OK
```

##### 错误返回
