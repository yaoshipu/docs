## 创建服务模板

#### 注意事项

- 需要`admin`权限

#### 请求

```
POST /api/templates/services
```

##### 请求参数

```json
{
  "service_name": "demo",
  "yaml": "yaml file content"
}
```
##### 参数说明

| 参数 | 描述 |
|-----|------|
| service_name | 服务名称，全局唯一 |
| yaml | 服务kube配置文件，示例如下 |
| test | 配置测试服务额外字段 |

```yaml
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  name: fe-financial
spec:
  rules:
  - host: {{.Service}}-{{.Namespace}}.ke-cs.dev.qiniu.io
    http:
      paths:
      - backend:
          serviceName: portal-v4-fe-financial
          servicePort: 80
        path: /
---
apiVersion: v1
kind: Service
metadata:
  name: portal-v4-fe-financial
spec:
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  selector:
    s-product: {{.Product}}
    s-group: {{.Group}}
    s-service: {{.Service}}
  clusterIP: None
---
apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: portal-v4-fe-financial
spec:
  replicas: 1
  template:
    spec:
      imagePullSecrets:
        - name: qn-registry-secret
      containers:
        - image: index.qiniu.com/spocket/test:latest
          imagePullPolicy: Always
          name: fe-financial
          ports:
            - protocol: TCP
              containerPort: 80
```

##### 正常返回

```
200 OK
```

##### 错误返回

```json
{
  "code":6101,
  "message":"Create Template Error",
  "description":"error details"
}
```