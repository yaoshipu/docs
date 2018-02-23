## 更新通知

#### 注意事项

- 需要`admin`权限
- 只能修改type为1的系统通知

#### 请求

```
PUT /api/notify/update
```

##### 请求参数

```json
{
    "id":"5a45b0a1c2c4ea0001d76705",
    "type": 1,
    "receiver": "*",
    "content": {
        "title": "test",
        "priority":1,
        "content":"dajiahao",
        "start_time":1514476800,
        "end_time":1517328000
    }
}
```

##### 参数说明

|参数|描述|
|---|---|
|type|`1`对应系统通知|
|receiver|*为系统通知|
|content|消息内容|

##### 正常返回

```
200 OK
```

##### 错误返回
