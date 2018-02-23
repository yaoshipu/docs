## 列出仓库 web hooks

#### 注意事项

- 需要`admin`权限

#### 请求

```
GET /api/repos/:owner/:repo/hooks
```

##### 请求参数

无

##### 正常返回

```json
[
    {
        "created_at": "2018-02-23T13:49:10Z",
        "updated_at": "2018-02-23T13:49:10Z",
        "name": "web",
        "url": "https://api.github.com/repos/qbox/aslan-platform/hooks/22560382",
        "events": [
        "pull_request",
        "push"
        ],
        "active": true,
        "config": {
        "content_type": "json",
        "insecure_ssl": "0",
        "secret": "********",
        "url": "https://spock-dev.qiniu.io/api/githubhook"
        },
        "id": 22560382
    }
]
```

##### 错误返回
