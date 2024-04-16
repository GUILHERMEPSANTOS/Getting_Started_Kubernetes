# Comandos Úteis do Kubernetes

## Listando Todos os Recursos do Kubernetes e Suas Versões

Para listar todos os recursos disponíveis no Kubernetes juntamente com suas versões, você pode utilizar o seguinte comando:

kubectl api-resources

## Campos

apiVersion: 
kind:     
metadata:
  name: 
spec:
  containers:
  - name: 
    image: 
    ports: 
    - containerPort: 

**Campos:**

- **apiVersion:** Especifica a versão da API do Kubernetes que será usada para criar o objeto.
- **kind:** Define o tipo de objeto que será criado, como Pod, Deployment, Service, etc.
- **metadata.name:** Nome do objeto a ser criado.
- **spec.containers:** Lista de contêineres a serem incluídos no objeto.
  - **name:** Nome do contêiner.
  - **image:** Nome da imagem Docker a ser usada para o contêiner.
  - **ports:** Lista de portas que o contêiner expõe.
    - **containerPort:** Número da porta no contêiner que será exposta.

## Criar um Pod Simples:

```shell
 kubectl create -f pod.yml
```

Verifique o estado do pod com 

```shell
 kubectl get pods   

 kubectl describe pod <nome do pod>
```

Para ver o resultado

```shell
 kubectl port-forward pod/processing-large-reports-in-browser-pod 8080:3000
```

