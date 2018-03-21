## 获取质量现状insights

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/insights/quality/:boardname
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
{
    "board_name": "test",
    "errors": [],
    "ut_coverage": 42.672886,
    "it_coverage": 0.17699985,
    "it_average_run_time": 19.968916,
    "worst_ut_ranks": [
        {
            "repo_name": "pay",
            "rate": 43.656754
        },
        {
            "repo_name": "iam",
            "rate": 64.31023
        }
    ],
    "worst_it_ranks": [
        {
            "repo_name": "pricedCovs",
            "rate": 0.20979021
        },
        {
            "repo_name": "tradedCovs",
            "rate": 0.22163886
        }
    ],
    "p2_bugs": 0,
    "unsolved_p2_bugs": 0,
    "external_bugs": 0,
    "unsolved_external_bugs": 0,
    "incidents": 0,
    "unsolvedIncidents": 0,
    "follow_up_incidents": 0,
    "history_follow_up_incidents": 0,
    "update_time": 1521623557
}
```

##### 错误返回
