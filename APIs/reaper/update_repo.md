## 更新Git仓库配置

#### 注意事项

- 需要`admin`权限
- 注意所有参数都为可选项

#### 请求

```
PUT /api/repos/:owner/:name
```

##### 请求参数

```json
{
    "trusted": true,
    "allow_pr": true,
    "allow_push": true,
    "allow_deploys": true,
    "allow_tags": true
}
```	

##### 参数说明

无

##### 正常返回

```json
{
    "id": 16,
    "owner": "yaoshipu",
    "name": "aone",
    "full_name": "yaoshipu/aone",
    "avatar_url": "https://avatars0.githubusercontent.com/u/13618151?v=4",
    "link_url": "https://github.com/yaoshipu/aone",
    "scm": "git",
    "clone_url": "https://github.com/yaoshipu/aone.git",
    "default_branch": "develop",
    "timeout": 60,
    "visibility": "private",
    "private": true,
    "trusted": true,
    "gated": false,
    "allow_pr": true,
    "allow_push": true,
    "allow_deploys": true,
    "allow_tags": true,
    "config_file": ".drone.yml"
}
```

##### 错误返回
