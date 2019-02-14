Agora que temos nossa imagem docker publicada no Docker Hub (ou em outro registry), podemos fazer o deploy dela no nosso kubernetes.

Para isso, rode:
`kubectl create deployment hello-node --image={NOME_DO_USUARIO_DOCKER}/hello-world`{{execute}}

Para você ver o deploy, rode:
`kubectl get deployments`{{execute}}

Output:
```
NAME         DESIRED   CURRENT   UP-TO-DATE   AVAILABLE   AGE
hello-node   1         1         1            1           1m
```
(Ou de uma olhada na dashboard)


Podemos também analisar os pods:
`kubectl get pods`{{execute}}

Output:
```
NAME                          READY     STATUS    RESTARTS   AGE
hello-node-5f76cf6ccf-br9b5   1/1       Running   0          1m
```


E para os eventos:
`kubectl get events`{{execute}}

Também é possível ver as configurações do kubectl:
`kubectl config view`{{execute}}
