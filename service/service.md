# Service

No Kubernetes, um serviço é um método para expor um aplicativo de rede que está sendo executado como um ou mais pods em seu cluster.

```shell
kubectl apply -f <service-file>.yaml 
```

Sempre verifique se as labels estão de acordo com o ``ReplicaSet`` ou outro serviço

``ReplicaSet``

```yaml

 selector: 
    matchLabels:
      app.kubernetes.io/name: processing-large-reports-in-browser
      app.kubernetes.io/part-of: node.js

```

``Service``

```yaml

 selector:
      app.kubernetes.io/name: processing-large-reports-in-browser
      app.kubernetes.io/part-of: node.js

```



# Minikube

Para acessar aplicativos em execução dentro do minikube
Existem duas categorias principais de serviços no Kubernetes: ``NodePort`` e ``LoadBalancer``. O minikube suporta ambos.


 **``Acesso NodePort``**

Um serviço NodePort é a maneira mais básica de obter tráfego externo diretamente para seu serviço. Ele abre uma porta específica, e todo o tráfego enviado para essa porta é encaminhado para o serviço.

Como obter o NodePort usando o comando service
Há também um atalho para obter o IP do minikube e o NodePort de um serviço:

```shell
minikube service <nome-do-serviço> --url
```



