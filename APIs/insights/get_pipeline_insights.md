## 获取工作流insights

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/insights/pipeline/:boardname
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
{
    "board_name":"test",
    "total":81,
    "total_average_pass_rate":0,
    "tendency_total_run_count":[
        {
            "value":80,
            "time":1520405461
        },
        {
            "value":80,
            "time":1520406065
        }
    ],
    "tendency_total_average_run_time":[
        {
            "value":147,
            "time":1520405461
        },
        {
            "value":147,
            "time":1520406065
        }
    ],
    "update_time":0
}
```

##### 错误返回
