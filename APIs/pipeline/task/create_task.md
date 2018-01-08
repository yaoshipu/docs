## 创建任务

#### 注意事项

- 需要`user`权限
- image格式
  - 格式1: index.qiniu.com/spocktest/spock-backend:20171010142156-develop
  - 格式2: index.qiniu.com/spocktest/spock-backend:20171010142156-pr123
  - spock-backend 为二进制或者服务名称
  - 20171010142156 为时间戳精确到秒
  - develop 为分支名称
  - pr123 为Git PR

- package_file 格式
  - spock-backend-20171010142156-develop.tar.gz
  - spock-backend-20171010142156-pr123.tar.gz

#### 请求

```
POST /api/tasks
```

##### 请求参数

```json
{
  "type": "pipeline",
  "pipeline_name": "demo-pipeline",
  "info": {
    "product_name": "spock-kube",
    "group_name": "spock-kube",
    "service_name": "spock-backend",
    "container_name": "spock-backend"
  },
  "sub_tasks": [
    {
      "type": "build",
      "repo_owner": "qbox",
      "repo_name": "aslan-platform",
      "branch": "dev",
      "pull_request_number": 123,
      "commit_id": "456",
      "bin": "spock-backend",
      "image": "index.qiniu.com/spocktest/spock-backend:1.0.3",
      "package_file": "build service kodo package file",
      "package_dir": "build service kodo package file",
      "dependency_builds": [
        {
          "repo_owner": "qbox",
          "repo_name": "aslan-platform",
          "branch": "master",
          "pull_request_number": 11
        }
      ]
      "timeout": 7200
    },
    {
      "type": "buildv2",
      "enabled": true,
      "build_os": "trusty",
      "job_ctx": {
        "clean_workspace": false,
        "scripts": "set -e
          printenv
          go version
          export PKG_DIR=$WORKSPACE/src/github.com/qbox/aslan-platform/_package
          echo $PKG_DIR
          mkdir -p $PKG_DIR
          export GOPATH=$WORKSPACE
          cd $WORKSPACE/src/github.com/qbox/aslan-platform
          make deps-cache clean-spock build-spock-net
          make depinstall-spock-portal build-spock-portal
          cd spock/cmd/spock
          docker build --rm -t $IMAGE -f Dockerfile .
          docker push $IMAGE
          cp ./spock $PKG_DIR
          tar -czvf $DIST_DIR/$PKG_FILE $PKG_DIR",
        "envs": [
          "TEST_ENV=ABC"
        ],
        "package_file": "spock-backend-test-0105-2.tar.gz",
        "image": "index.qiniu.com/spocktest/spock-backend-test:01052",
        "builds": [
          {
            "repo_owner": "qbox",
            "repo_name": "aslan-platform",
            "branch": "develop",
            "pr": 0,
            "commit_id": "",
            "commit_message": "",
            "checkout_path": "/src/github.com/qbox",
            "remote_name": "origin",
            "submodules": false
          }
        ]
      },
      "install_items": [
        {
          "name": "go",
          "version": "1.8.3"
        },
        {
          "name": "glide",
          "version": ""
        },
        {
          "name": "node",
          "version": "6.11.2"
        },
        {
          "name": "yarn",
          "version": ""
        }
      ]
    }, 
    {
      "type": "deploy",
      "namespace": "yaoshipu",
      "product_name": "spock-kube",
      "group_name": "spock-kube",
      "service_name": "spock-backend",
      "container_name": "spock-backend",
      "image": "same as previous build task value",
      "package_file": "same as previous build task value",
      "timeout": 600
    },
    {
      "type": "testing",
      "product_name": "spock-kube",
      "group_name": "spock-test",
      "service_name": "spock-backend-test",
      "container_name": "spock-backend-test",
      "threshold": 90,
      "command": "command to run test",
      "result_path": "test result path",
      "timeout": 3600
    },
    {
      "type": "distribute",
      "dist_host": "jumpbox",
      "package_file": "same as previous build task value",
      "timeout": 600
    },
    {
      "type": "jira",
      "repo_owner": "qbox",
      "repo_name": "aslan-platform",
      "pull_request_number": 123,
      "timeout": 600
    }
  ]
}
```

##### 参数说明

|key|value|
|---|---|
|pipeline_name|工作流名称|
|repo_name|代码库名称|
|repo_owner|代码库所有人|
|branch|代码编译分支 如果提供了pull_request_number, branch会被忽略|
|pull_request_number|pull request number|
|commit_id|commitID 如果是提交PR, 则需要提供|
|install_ctx| 全部可选 |
|build_os| precise, trusty, xential |

##### 正常返回

```
200 OK
```

##### 错误返回
