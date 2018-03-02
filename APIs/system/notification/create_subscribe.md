## 创建(更新)关注

#### 注意事项

- 需要`user`权限

#### 请求

```
POST /api/notify/subscribe
```

##### 请求参数

```json
{
    "type": 2,
    "pipelinestatus":"passed"
}
```

##### 参数说明

|参数|描述|
|---|---|
|type|`1`对应系统通知，`2`对应pipline提醒，`3`对应message|
|pipelinestatus|`passed`关注pipeline通过信息，`failed`关注失败信息，`*`关注所有信息|

##### 正常返回

```
200 OK
```

##### 错误返回
