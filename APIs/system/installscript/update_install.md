## 更新安装脚本

#### 注意事项

- 需要`admin`权限

#### 请求

```
PUT /api/install/:name/:version
```

##### 请求参数

```json
{
  "scripts": "curl -fsSL http://spock-resources.qbox.net/go1.8.3_fix.linux-amd64.tar.gz -o /tmp/golang.tar.gz\ntar -C /usr/local -xzf /tmp/golang.tar.gz",
  "env": [
    "GOROOT=/usr/local/go",
    "GOPATH=/go"
  ],
  "bin_path": "/usr/local/go/bin",
  "name": "go",
  "version":"1.8.3_fix",
  "desc": "golang 1.8.3_fix",
  "enabled": true
}

```

##### 参数说明

|参数|描述|
|---|---|
|scripts|安装脚本|
|env|环境变量|
|binpath|默认binpath|
|name|脚本名称|
|version|脚本版本|
|desc|脚本描述|
|enabled|是否启用|



##### 正常返回

```
200 OK
```

##### 错误返回
## 更新安装脚本

#### 注意事项

- 需要`admin`权限

#### 请求

```
PUT /api/install/:name/:version
```

##### 请求参数

```json
{
  "scripts": "curl -fsSL http://spock-resources.qbox.net/go1.8.3_fix.linux-amd64.tar.gz -o /tmp/golang.tar.gz\ntar -C /usr/local -xzf /tmp/golang.tar.gz",
  "env": [
    "GOROOT=/usr/local/go",
    "GOPATH=/go"
  ],
  "bin_path": "/usr/local/go/bin",
  "name": "go",
  "version":"1.8.3_fix",
  "desc": "golang 1.8.3_fix",
  "enabled": true
}

```

##### 参数说明

|参数|描述|
|---|---|
|scripts|安装脚本|
|env|环境变量|
|binpath|默认binpath|
|name|脚本名称|
|version|脚本版本|
|desc|脚本描述|
|enabled|是否启用|



##### 正常返回

```
200 OK
```

##### 错误返回
