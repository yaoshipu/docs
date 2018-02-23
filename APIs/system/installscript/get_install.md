## 查询安装脚本

#### 注意事项

- 需要`admin`权限

#### 请求

```
GET /api/install/:name/:version
```

##### 请求参数

|参数|描述|
|---|---|
|name|脚本名称|
|version|脚本版本|


##### 参数说明

无

##### 正常返回

```json
  {
        "name": "node",
        "version": "6.11.2",
        "desc": "node 6.11.2",
        "scripts": "curl -fsSL http://spock-resources.qbox.net/node-v6.11.2-linux-x64.tar.gz -o /tmp/node.tar.gz\ntar -C /usr/local -xzf /tmp/node.tar.gz --strip-components=1\nnpm config --global set registry https://registry.npm.taobao.org",
        "update_time": 1515122063,
        "update_by": "yaoshipu",
        "enabled": true
    }
```

##### 错误返回
