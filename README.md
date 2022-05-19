# Projeto Rotten Tomatoes Microsserviços

## Estrutura do projeto
Esse projeto é baseado em uma aquitetura de Microsserviços e depende de outros 2 projetos pra funcionar

- [Serviço de Filmes](https://github.com/kubedev/movie)
- [Serviço de Review](https://github.com/kubedev/review)

Segue abaixo o diagrama:

![Diagrama da solução](./img/diagrama.png)

## Configuração

MOVIE_SERVICE_URI => URL de acesso ao serviço de listagem de filmes

REVIEW_SERVICE_URI => URL de acesso ao serviço de listagem de reviews

Exemplo:

MOVIE_SERVICE_URI: http://movies:8181

REVIEW_SERVICE_URI: http://review:8282 <<<<=========


A aplicação review escuta na porta 80, muito embora se faça no docker-compose.yaml redirecionar a porta do 
Container para 8282:80, a aplicação rotten-potatoes não consegue acessar o micro servico view na porta 8282
Portanto para que o conjunto funcione fui obrigado a apontar :

REVIEW_SERVICE_URI: http://review <<<<=== porta 80 serviço defaul web.


