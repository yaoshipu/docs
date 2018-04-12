## 列出任务V2


#### 注意事项

* 需要`user`权限

#### 请求

```
GET /api/v2/tasks/max/:max/start/:start/pipelines/:pipelinename
```

##### 请求参数

|参数|说明|
|---|---|
|max|每页最大个数|
|start|第几个开始取|



##### 正常返回

```json

{
    "data": [
        {
            "task_id": 8,
            "task_creator": "guoyu",
            "pipeline_name": "0323",
            "status": "failed",
            "create_time": 1523527145,
            "start_time": 1523527146,
            "end_time": 1523527491
        },
        {
            "task_id": 7,
            "task_creator": "guoyu",
            "pipeline_name": "0323",
            "status": "passed",
            "create_time": 1522832278,
            "start_time": 1522832279,
            "end_time": 1522832515
        }
    ],
    "start_at": 1,
    "max_resault": 2,
    "total": 8
}

```

##### 错误返回





