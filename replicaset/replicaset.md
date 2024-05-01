# ReplicaSet

O objetivo de um ``ReplicaSet`` é manter um conjunto estável de pods de réplica em execução a qualquer momento. Como tal, é frequentemente usado para garantir a disponibilidade de um número específico de Pods idênticos.

Para criar o ``ReplicaSet``:

```shell

kubectl apply -f <replicaset-file>.yaml 
```

``Configurações ReplicaSet``

 ```yaml
spec:
  replicas: 3  # Quantidade de pods replicados
  selector:
    matchLabels:  # Seleciona e controla pods com estes rótulos
      app.kubernetes.io/name: processing-large-reports-in-browser
      app.kubernetes.io/part-of: node.js
  template:  # Configuração dos pods
    metadata:
      labels:
        app.kubernetes.io/name: processing-large-reports-in-browser
        app.kubernetes.io/part-of: node.js
    spec:
      containers:
      - name: processing-large-reports-in-browser
        image: gulhermepsantos/processing-large-reports-in-browser:latest
        ports:
        - containerPort: 3000

```          
