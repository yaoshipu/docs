## 列出insights config

#### 注意事项

- 需要`admin`权限

#### 请求

```
GET /api/insights/config
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
[
 {
    "board_name": "test", 
    "github_config": {
        "enabled": true, 
        "repo_names": [
            "aslan", 
            "kodo"
        ]
    }, 
    "project_config": {
        "enabled": true, 
        "jira_project_name": "aslan", 
        "jira_project_id": 123, 
        "jira_board_name": "spock", 
        "jira_board_id": 112, 
        "bugs_query": "", 
        "unresolved_bugs_query": "", 
        "tasks_query": "", 
        "unresolved_tasks_query": ""
    }, 
    "quality_config": {
        "enabled": true, 
        "ut_team": "aslan", 
        "st_team": "spock", 
        "p2_bugs_query": "", 
        "unsolved_p2_bugs_Query": "", 
        "external_bugs_query": "", 
        "unsolved_external_bugs_query": "", 
        "incidents_query": "", 
        "unsolved_incidents_query": "", 
        "follow_up_incidents_query": "", 
        "history_follow_up_incidents_query": ""
    }, 
    "pipeline_config": {
        "enabled": true, 
        "team": [
            "kodo", 
            "aslan"
        ]
    }, 
    "deploy_config": {
        "enabled": true, 
        "deploy_issues_query": "", 
        "completed_deploy_issues_query": ""
    }
}
]
```

##### 错误返回
