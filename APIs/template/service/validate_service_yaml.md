## 检查服务模板Yaml

#### 注意事项

- 需要`user`权限

#### 请求

```
POST /api/templates/validate
```

##### 请求参数

```json
{
  "service_name": "svc1",
  "yamls": ["parsed yaml 1", "parsed yaml 2"]
}
```

##### 参数说明

无

##### 正常返回

```json
{
  "message": "success"
}
```

##### 错误返回

```json
{
  "code": 6105,
  "description": "convert yaml file [0] error: Run command: kubectl convert -f /tmp/spec_test_1.yaml -o json --kubeconfig /spock/.kube/config failed. error: unable to decode \"/tmp/spec_test_1.yaml\": Object 'Kind' is missing in '{\"apiVersion\":\"v1\",\"kind1\":\"Secret\",\"metadata\":{\"data\":null,\"github.access.token\":\"godoc.github.access.token\",\"name\":\"godoc-secret\",\"namespace\":\"godoc\",\"type\":\"Opaque\"}}'\n",
  "message": "validate template error",
  "type": "error"
}
```