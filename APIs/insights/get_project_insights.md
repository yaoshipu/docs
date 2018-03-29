## 获取项目进度insights

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/insights/project/:boardname
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
{
    "board_name": "aslan", 
    "errors": {
    "time_consumed_rate":"team []not found"
    },
    "time_consumed_rate" : 0.3591993749141693,
    "completed_rate" : 0.1666666716337204,
    "current_sprint": {
        "id": 1, 
        "name": "ASLAN", 
        "start_time": 12232343, 
        "end_time": 123446898, 
        "new_issues": 3, 
        "process_issues": 5, 
        "completed_issues": 8
    }, 
    "user_progress": [
        {
            "user_name": "guoyu", 
            "new_issues": 3, 
            "process_issues": 6, 
            "completed_issues": 5,
            "completed_rate" : 0.1666666716337204
        }
    ], 
    "bugs": 5, 
    "unresolved_bugs": 2, 
    "tasks": 10, 
    "unresolved_tasks": 4, 
    "update_time": 1234567886
}
```

##### 错误返回
