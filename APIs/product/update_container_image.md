## 更新容器镜像

#### 注意事项

#### 请求

##### 请求参数

```json
{
  "kind": "pod",
  "resource_name": "pod_name",
  "container_name": "container_name",
  "image": "image_full_name"
}
```

##### 参数说明

|参数|描述|
|---|---|
|kind|kube资源类型|
|resource_name|kube资源名称|
|container_name|容器名称|
|image|镜像|

##### 正常返回

```
200 OK
```

##### 错误返回
