## 更新insights config

#### 注意事项

* 需要admin权限
* boardName名字不能修改

#### 请求

```
PUT /api/insights/config/:boardname
```

##### 请求参数

```json
{
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
```


##### 正常返回

```
200 OK
```

##### 错误返回



