## 查询服务配置

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/configmaps/:name
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
{
  "name": "apps-api-configmap",
  "age": "27d",
  "labels": {
    "s-group": "portal-v4",
    "s-product": "portal-v4",
    "s-service": "index"
  },
  "data": {
    "apps-api": "run_mode = staging\nhttp_addr = 0.0.0.0\nhttp_port = 3009\n\nsecret = YT9hu3ILHgcoSYTg42FBInYtojLxQhkv1Mnc0CuIKLtRu58FQxYHbRRt1jea414a\n\ncookie_prefix = PORTAL\ncookie_secure = false\n\nadmin_username = root\nadmin_password = root\n\n# 由appd颁发\nadmin_access_key = portal_access_key\nadmin_secret_key = portal_secret_key\n\n[audit_log]\nlog_dir = ../run/log/auditlog/portalv4apps\nchunk_bits = 29\nbody_limit = 256\nmodule_name = APPS\n\n[mongo]\ndb.sess = mongodb://10.200.20.23:27017/qbox_sess\n\n[service]\napp_host = http://app-api.cs.qiniu.io\naccount_host = http://10.200.20.25:9100\nportal_mgr_host = http://10.200.20.33:2604\n"
  }
}
```

##### 错误返回
