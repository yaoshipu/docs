## 列出Agent状态

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/v2/status/agents
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
[
  {
    "agent": "Warpdrive 130744",
    "messages_received": 0,
    "messages_finished": 0,
    "messages_requeued": 0,
    "connections": 1,
    "is_busy": false,
    "start_time": 1507957664,
    "update_time": 1507957753
  }
]
```

##### 错误返回
