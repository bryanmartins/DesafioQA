# Desafio QA BACKEND

# Sobre o desafio 

O desafio tem a finalidade de avaliar os testes nos fluxos de Extrato, Saldo e Transferência Interna através da nossa API Pública.


## Testes de API

Sua missão é desenvolver alguns testes para a nossa API pública:

### Instruções iniciais

Para você desenvolver o desafio, utilize a seguinte conta que foi criada no nosso ambiente de Sandbox com dados fictícios.

- username - desafioqastone@gmail.com
- password - desafioqa

Você consegue acessar sua conta por esse link: https://sandbox.conta.stone.com.br/login.

Pronto! Você já está pronto para começar seu desafio.

Para se logar pela linha de comando, basta usar o seguinte comando:

```
curl https://login.sandbox.stone.com.br/auth/realms/stone_account/protocol/openid-connect/token \
	  -d 'client_id=admin-cli' \
	  -d 'username=YYYYYYYYY' \
	  -d 'password=ZZZZZZZZZ' \
          -d 'grant_type=password'
```

Isso te devolverá um `access_token`. Use-o para se autenticar nas chamadas para a API.

Você pode fazer transferências internas para essa conta:  
- Stone: 197  
- Agência: 0001  
- Conta: 475384


### Cenário

A Stone possui uma API de [OpenBanking](https://en.wikipedia.org/wiki/Open_banking) que estamos testando e evoluindo continuamente. O link para a documentação de referência é https://docs.openbank.stone.com.br/. 

Queremos que você use esta API para nos mostrar como iria automatizar as várias formas de se inferir qualidade das entregas.

Por exemplo: temos um endpoint para simular uma transação interna em `api/v1/dry_run/internal_transfers`. Queremos que você proponha uma solução de automação neste ambiente de "sandbox" da API. 

Espera-se que você faça a automação de 3 endpoints:

- Saldo: `GET api/v1/accounts/:id/balance`
- Extrato: `GET api/v1/accounts/:id/statement`
- Simulação de transferência interna: `POST api/v1/dry_run/internal_transfers`

Os dados para acesso serão detalhados mais abaixo.

### Como operar na API de sandbox da Stone OpenBanking?

Todos os endpoints possuem autenticação. Utilizamos OAuth2 e OpenID Connect como especificações de autenticação e autorização. Para o desafio de QA, criamos uma "client application" e um usuário para os testes:

- client_id: XXXXXXXXXX
- username: YYYYYYYY
- password: ZZZZZZZZ

Para conseguir o token de acesso, basta fazer um POST para o nosso IAM:

```
curl https://login.sandbox.stone.com.br/auth/realms/stone_account/protocol/openid-connect/token \
	  -d 'client_id=XXXXXXXXXX' \
	  -d 'username=YYYYYYYYY' \
	  -d 'password=ZZZZZZZZZ' \
          -d 'grant_type=password'
```
### Informações sobre a etapa

   - Utilizar o formato Gherkin para a descrever os casos de teste das APIs;
   - Os casos de testes devem ser construídos através do Postman;
   - O desafio deve conter, no mínimo, um projeto de código que instrumente o uso da API seguindo um conjunto de cenários que você mesmo irá criar para os 3 endpoints citados acima;
   - A execução deve retornar um status;
   - Ao término da execução deve ser gerado um relatório sobre as APIs testadas (cenários com sucesso/falha, timing, security e etc);

### Critérios de Avaliação

 Levaremos em conta os seguintes fatores:

  - Detalhamento e Organização;
  - Uso correto do Gherkin;
  - Conhecimento de APIs;
  - Uso dos Testes no Postman;
  - Escrita de cenários sobre os endpoints;
  - Coleta de evidências da execução;


# Envio do Desafio

 Você deve disponibilizar seu código no Github e manter o repositório como privado. Quando finalizar, favor entrar em contato com a sua recrutadora, para disponibilizarmos os usuários que deverão possuir acesso para realizar a avaliação.


O repositório deve ser facilmente executável! E lembre-se, a organização e o nível de detalhamento da entrega serão cruciais nesta avaliação!

Bom desafio! 
