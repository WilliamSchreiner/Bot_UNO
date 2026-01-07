# UNO Bot

## Visão Geral
O UNO Bot é uma API simples responsável por tomar decisões de jogo no UNO. A API recebe o estado atual da rodada (última carta jogada e cartas na mão do BOT) e retorna qual carta deve ser jogada de acordo com as regras oficiais do UNO.

O foco do projeto é tomada de decisão determinística, um algoritmo que em sua primeira versão, garanta baixo custo de desenvolvimento e fácil entendimento acadêmico.

## Objetivo do Projeto
* Simular a tomada de decisão de um jogador de UNO
* Trabalhar conceitos de API REST, arquitetura em camadas e lógica de decisão
* Criar um módulo reutilizável (biblioteca)
* Integrar futuramente com um jogo UNO desenvolvido ou continuar aprimorando para conceitos mais complexos, como presições e jogadas mais elaboradas

## Tecnologias
### Linguagem
JavaScript (Node.js)
### Motivo:
- Não quero matar uma mosca com uma bazuca, como Java ou C# e ele tem um excelente suporte a APIs
### Framework
Express.js – criação do servidor HTTP
### Documentação
Swagger (OpenAPI)
* swagger-ui-express
* swagger-jsdoc

## Arquitetura do Projeto

* API Layer – Recebe requisições HTTP
* Controller – Coordena fluxo da requisição
* Service (Decision Engine) – Contém a lógica do algoritmo
* Utils / Rules – Regras do UNO e funções auxiliares

## Modelo de Dados (JSON)

Exemplo request body;
```
{
"lastCard": {
"color": "red",
"value": "5"
},
"hand": [
{ "color": "red", "value": "7" },
{ "color": "blue", "value": "5" },
{ "color": "wild", "value": "wild" }
]
}
```
Exemplo response body;
```
{
"chosenCard": {
"color": "red",
"value": "7"
},
"reason": "Mesma cor da última carta"
}
```

## Endpoints

POST /decision
Objetivo: Retorna a melhor carta para jogar

GET /generate
Objetivo: Retorna um exemplo de mão aleatoria padrão (7 cartas)


