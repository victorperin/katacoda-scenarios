Minikube já está instalado nesse ambiente, mas você pode instala-lo na sua maquina seguindo [suas instruções](https://kubernetes.io/docs/tasks/tools/install-minikube/):

Para verificar se ele está instalado, você pode usar o comando:
`minikube version`{{execute}}

Inicie um novo cluster kubernetes rodando o comando:

`minikube start`{{execute}}

Legal! Agora temos um cluster Kubernetes rodando no seu terminal. Minikube criou uma maquina virtual para você e um cluster kubernetes está rodando nessa VM.

Agora, rode o comando: `kubectl get nodes`{{execute}}

Aguarde um output desse tipo:
```
NAME       STATUS    ROLES     AGE       VERSION
minikube   Ready     <none>    10s       v1.10.0
```
Caso o `STATUS` esteja como `NotReady`, por favor, aguarde um pouco e rode o comando anterior novamente, até que o `STATUS` esteja `Ready`.

Com isso, agora temos um nó do kubernetes rodando em nossa maquina (você pode rodar o minikube na sua maquina também, em um ambiente local).

Vamos agora abrir a dashboard do kubernetes rodando `minikube dashboard`{{execute}}

Agora é só [acessar aqui](https://[[HOST_SUBDOMAIN]]-30000-[[KATACODA_HOST]].environments.katacoda.com/) (ou, se estiver rodando local, na sua porta 30000).

(mantenha essa guia aberta, assim poderemos verificar algumas coisas de maneira rápida e simples)
