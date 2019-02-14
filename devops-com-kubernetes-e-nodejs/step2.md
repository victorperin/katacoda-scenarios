Agora, com nosso cluster rodando, vamos nos preocupar com nossa aplicação.
A idéia é rodar uma aplicação simples por enquanto e, depois, faze-la aparecer no nosso cluster.

Iremos colocar uma api que responde `Hello World!` inicialmente, pois queremos focar no kubernetes.

#### Antes de tudo, precisamos criar uma conta no [Docker Hub](https://hub.docker.com).


#### Crie um arquivo chamado server.js com o seguinte conteudo:
```js
const http = require('http');

const handleRequest = (request, response) => {
  console.log(`Received request for URL: ${request.url}`);
  response.writeHead(200);
  response.end('Hello World!');
};

const server = http.createServer(handleRequest);
server.listen(8080);
```

#### Crie outro arquivo chamado Dockerfile com o seguinte conteúdo:
```docker
FROM node:6.14.2
EXPOSE 8080
COPY server.js .
CMD node server.js
```

Agora vamos construir a imagem do docker desse projeto, rode:

`docker build -t {NOME_DO_USUARIO_DOCKER}/hello-world .`{{execute}}

`docker login`{{execute}}
(coloque seu nome de usuario e senha do dockerhub)

`docker push {NOME_DO_USUARIO_DOCKER}/hello-world`{{execute}}

Pronto, você publicou sua primeira imagem no docker hub, você pode ve-la [aqui](https://hub.docker.com). (Se estiver logado)
