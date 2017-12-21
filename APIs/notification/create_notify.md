## 创建通知

#### 注意事项

- 需要`admin`权限

#### 请求

```
POST /api/notify
```

##### 请求参数

```json
{
  "type": 1,
  "receiver": "*",
  "content": {
    "title": "test",
    "priority":1,
    "content":"dajiahao",
    "start_time":1513565352,
    "end_time":1513569384
  }
}
```

##### 参数说明

|参数|描述|
|---|---|
|type|`1`对应系统通知，`2`对应pipline提醒|
|receiver|用户名（当用户名为*时为系统通知）|
|content|消息内容|

##### 正常返回

```
200 OK
```

##### 错误返回
