Por padrão, pods só podem ser acessados pelo endereço IP interno com o Kubernetes.

Para que nosso container `hello-world` seja acessível por fora da rede virtual do Kubernetes, precisamos exportar o `Pod` como um `Kubernetes Service`.


1- Exponha o Pod para a internet usando o comando:
`kubectl expose deployment hello-world --type=LoadBalancer --port=8080`{{execute}}

A flag `--type=LoadBalancer` indica que você quer exportar seu pod para fora do cluster.


2- Para ver o service que você criou, rode:
`kubectl get services`{{execute}}

Output:
```
NAME         TYPE           CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
hello-node   LoadBalancer   10.108.144.78   <pending>     8080:30369/TCP   21s
kubernetes   ClusterIP      10.96.0.1       <none>        443/TCP          23m
```

Em provedores de cloud (Gcloud, AWS, Azure, etc) que suportam load balancers, seria provisionado um endereço IP externo para acessa-lo. Já no Minikube, o tipo `LoadBalancer` faz o serviço acessível pelo comando:

`minikube service hello-world`{{execute}}
