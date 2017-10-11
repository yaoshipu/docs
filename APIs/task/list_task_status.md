## 列出任务状态

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/v2/tasks/status
```

##### 请求参数

- name: pipeline 名称
- limit: 显示任务数量

##### 参数说明

无

##### 正常返回

```json
[
  {
    "task_id": 3,
    "task_creator": "yaoshipu",
    "pipeline_name": "test-pipeline",
    "status": "passed",
    "create_time": 1507719109,
    "start_time": 1507721237,
    "end_time": 1507721240
  },
  {
    "task_id": 2,
    "task_creator": "zhangdahe",
    "pipeline_name": "test-pipeline",
    "status": "created",
    "create_time": 1507718533,
    "start_time": 1507718533,
    "end_time": 1507718533
  }
]
```

##### 错误返回
