## 获取服务模板

#### 注意事项

#### 请求

##### 请求参数

##### 参数说明

##### 正常返回


```json
{
  "service_name": "mongo3.2",
  "revision": 8,
  "yaml": "apiVersion: v1\nkind: Service\nmetadata:\n  name: mongo\n  namespace: {{.Namespace}}\n  labels:\n    s-product: {{.Product}}\n    s-group: {{.Group}}\n    s-service: {{.Service}}\nspec:\n  ports:\n    - port: 27017\n      targetPort: 27017\n  selector:\n    s-product: {{.Product}}\n    s-group: {{.Group}}\n    s-service: {{.Service}}\n  clusterIP: None\n---\napiVersion: apps/v1beta1\nkind: StatefulSet\nmetadata:\n  name: mongo\n  namespace: {{.Namespace}}\n  labels:\n    s-product: {{.Product}}\n    s-group: {{.Group}}\n    s-service: {{.Service}}\nspec:\n  serviceName: mongo\n  replicas: 3\n  podManagementPolicy: Parallel\n  selector:\n    matchLabels:\n      s-product: {{.Product}}\n      s-group: {{.Group}}\n      s-service: {{.Service}}\n  template:\n    metadata:\n      labels:\n        s-product: {{.Product}}\n        s-group: {{.Group}}\n        s-service: {{.Service}}\n    spec:\n      imagePullSecrets:\n        - name: qn-registry-secret\n      containers:\n        - name: mongo\n          image: mongo:3.2\n          imagePullPolicy: Always\n          command: \n            - mongod\n          args:\n            - --replSet\n            - rs0\n            - --smallfiles\n            - --noprealloc\n          ports:\n            - protocol: TCP\n              containerPort: 27017 \n          volumeMounts:\n            - name: data\n              mountPath: /data/db\n      volumes:\n        - name: data\n          emptyDir: {}",
  "hash256": "84e1c479f679c7e04fc283482fdcecf81d1efce4f2e1bb478012a01d499a91c7",
  "create_time": 1505816729,
  "update_by": "yaoshipu",
  "containers": [
    {
      "name": "mongo",
      "image": "mongo:3.2"
    }
  ]
}
```

##### 错误返回
