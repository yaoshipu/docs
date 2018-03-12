## 获取团队统计信息

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/insights/team
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
[
    {
        "team": "FUSION",
        "pipelines": [],
        "ptasks": [],
        "p_tasks_daily_usage_rate": [],
        "p_tasks_pass_rate": []
    },
    {
        "team": "Pandora",
        "pipelines": [
            {
                "value":1,
                "time":1520405461
            }
        ],
        "ptasks": [
            {
                "value":80,
                "time":1520405461
            }
        ],
        "p_tasks_daily_usage_rate": [
            {
                "value":2,
                "time":1520405461
            }        
        ],
        "p_tasks_pass_rate": [
            {
                "value":0,
                "time":1520405461
            }
        ]
    }    
 ]
```

##### 错误返回
