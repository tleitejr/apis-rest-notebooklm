# Fundamentos de APIs REST com NotebookLM

Projeto desenvolvido como parte de um desafio prático de aprendizagem ativa com Inteligência Artificial, curadoria de fontes e organização do conhecimento.

## Sobre o projeto

Este caderno temático apresenta os principais conceitos relacionados ao desenvolvimento e ao consumo de APIs REST.

O estudo foi realizado com apoio do NotebookLM, utilizando fontes técnicas abertas, perguntas estratégicas e diferentes variações de prompts para comparar respostas, identificar dificuldades e consolidar o conhecimento.

## Objetivos de estudo

- Entender o que são APIs e como funcionam.
- Diferenciar REST de protocolo HTTP.
- Compreender o conceito de recurso em uma API.
- Relacionar métodos HTTP às operações de uma API.
- Aprender a interpretar códigos de status HTTP.
- Entender os conceitos de statelessness e idempotência.
- Conhecer boas práticas de criação de endpoints.
- Compreender a finalidade da especificação OpenAPI.
- Criar prompts reutilizáveis para revisar o conteúdo.

## Ferramenta utilizada

- NotebookLM
- GitHub
- Markdown
- Documentações técnicas abertas

## Curadoria de fontes

As fontes abaixo foram selecionadas para serem adicionadas ao NotebookLM:

1. **RFC 9110 — HTTP Semantics**

   Documento oficial que descreve a arquitetura, os conceitos e a semântica do protocolo HTTP.

2. **MDN Web Docs — Métodos de requisição HTTP**

   Material de referência sobre os métodos GET, POST, PUT, DELETE, PATCH, HEAD, OPTIONS e outros.

3. **OpenAPI Specification**

   Especificação para descrever APIs HTTP de maneira padronizada, permitindo gerar documentação, clientes, servidores e testes.

4. **REST API Tutorial — What is REST?**

   Material introdutório sobre REST, recursos, restrições arquiteturais, representações e hipermídia.

5. **REST API Tutorial — Richardson Maturity Model**

   Conteúdo complementar sobre os níveis de maturidade de APIs REST.

> As fontes foram escolhidas combinando documentos normativos, documentação técnica e materiais explicativos. As fontes normativas foram usadas como referência principal, enquanto os materiais introdutórios foram utilizados para facilitar a interpretação dos conceitos.

## Como as fontes foram utilizadas

As fontes foram organizadas no NotebookLM por assunto:

- `01-http-semantics`
- `02-metodos-http`
- `03-openapi`
- `04-conceitos-rest`
- `05-maturidade-rest`

A separação facilitou a comparação entre definições formais e explicações práticas.

## Perguntas estratégicas utilizadas

### Prompt 1 — Visão geral

```text
Explique o que é uma API REST para uma pessoa que conhece lógica de programação, mas ainda não trabalha com desenvolvimento web. Use uma explicação progressiva, começando pelos conceitos mais simples e avançando até recursos, endpoints e métodos HTTP. Utilize somente as fontes fornecidas.
```

### Prompt 2 — Comparação entre conceitos

```text
Compare REST, HTTP e API. Para cada conceito, apresente:
1. definição;
2. finalidade;
3. relação com os demais conceitos;
4. exemplo prático;
5. erro comum de interpretação.
Utilize referências às fontes usadas.
```

### Prompt 3 — Métodos HTTP

```text
Crie uma tabela com os métodos GET, POST, PUT, PATCH e DELETE. Informe:
- finalidade;
- exemplo de endpoint;
- se normalmente é idempotente;
- possível código de resposta;
- erro comum de uso.
Não invente informações que não estejam nas fontes.
```

### Prompt 4 — Estudo baseado em cenário

```text
Considere uma API de biblioteca com os recursos livros e usuários. Proponha endpoints REST para:
- listar livros;
- buscar um livro;
- cadastrar um livro;
- alterar completamente um livro;
- alterar parcialmente um livro;
- remover um livro.

Explique por que cada método HTTP foi escolhido.
```

### Prompt 5 — Revisão crítica

```text
Analise a afirmação: "Toda API que utiliza HTTP e JSON é automaticamente RESTful".

Diga se a afirmação está correta ou incorreta, explique o motivo e apresente um exemplo de API que utiliza HTTP, mas não segue completamente os princípios de REST.
```

### Prompt 6 — Avaliação do aprendizado

```text
Crie um quiz com 10 questões sobre APIs REST, contendo:
- 5 questões de múltipla escolha;
- 3 questões de verdadeiro ou falso;
- 2 questões discursivas.

Não mostre o gabarito inicialmente. Depois que eu responder, corrija minhas respostas e explique meus erros com base nas fontes.
```

## Engenharia de prompts e cicatrizes

Durante os testes, foi possível observar que a qualidade das respostas dependia bastante do nível de detalhamento do prompt.

### Teste 1 — Prompt genérico

```text
Explique APIs REST.
```

#### Resultado

A resposta foi ampla, mas apresentou muitos conceitos ao mesmo tempo e não deixou claro quais informações vieram das fontes.

#### Problema identificado

- Escopo muito amplo.
- Ausência de nível de conhecimento do estudante.
- Falta de exigência de referências.
- Falta de formato definido para a resposta.

### Teste 2 — Prompt com contexto

```text
Explique APIs REST para um estudante iniciante de desenvolvimento web. Organize a resposta em definição, funcionamento, exemplos e conceitos relacionados.
```

#### Resultado

A resposta ficou mais organizada e acessível, porém ainda apresentou pouca comparação entre REST e HTTP.

### Teste 3 — Prompt com restrições e fontes

```text
Explique APIs REST para um estudante iniciante. Organize a resposta nas seções definição, funcionamento, recursos, endpoints, métodos HTTP e códigos de status. Use somente as fontes carregadas no NotebookLM e indique qual fonte apoia cada parte da explicação. Caso uma informação não esteja nas fontes, informe isso explicitamente.
```

#### Resultado

A resposta apresentou melhor organização, maior rastreabilidade e menor risco de misturar conceitos externos às fontes.

### Principais dificuldades encontradas

- Confusão entre REST e HTTP.
- Uso dos termos PUT e PATCH como se fossem equivalentes.
- Interpretação incorreta de idempotência.
- Generalização de que toda API HTTP é RESTful.
- Respostas muito extensas quando o prompt não definia um formato.
- Ausência de referências quando o prompt não solicitava fontes.

### Soluções aplicadas

- Informar o nível de conhecimento do estudante.
- Definir o formato da resposta.
- Solicitar exemplos práticos.
- Determinar que a IA usasse somente as fontes carregadas.
- Pedir indicação das referências.
- Dividir perguntas grandes em etapas menores.
- Solicitar que a IA sinalizasse possíveis ambiguidades.

## Miniguia de estudo

### 1. O que é uma API?

API significa Application Programming Interface.

Uma API é um contrato de comunicação entre sistemas. Ela define como um cliente pode solicitar informações ou executar operações em um servidor.

Exemplo:

```http
GET /livros
```

Nesse exemplo, o cliente solicita a lista de livros disponibilizada pelo servidor.

Uma API pode ser utilizada por:

- aplicações web;
- aplicativos móveis;
- sistemas internos;
- dispositivos embarcados;
- outros serviços.

### 2. O que é REST?

REST significa Representational State Transfer.

REST não é uma linguagem de programação nem um protocolo. É um estilo arquitetural para projetar sistemas distribuídos.

Uma API orientada a REST geralmente:

- organiza dados como recursos;
- utiliza identificadores para os recursos;
- aproveita os métodos HTTP;
- mantém as requisições independentes;
- utiliza representações como JSON;
- utiliza códigos de status HTTP;
- pode utilizar hipermídia para orientar as próximas ações.

### 3. REST não é a mesma coisa que HTTP

HTTP é o protocolo utilizado para transportar requisições e respostas.

REST é um estilo arquitetural que pode utilizar HTTP como base de comunicação.

Uma aplicação pode utilizar HTTP sem seguir adequadamente os princípios REST.

### 4. Recursos e endpoints

Um recurso representa uma entidade ou informação do sistema.

Exemplos:

- usuários;
- produtos;
- pedidos;
- livros;
- pagamentos.

Um endpoint é um endereço utilizado para acessar um recurso.

Exemplos:

```text
/users
/users/42
/products
/products/10/orders
```

É recomendado utilizar substantivos nos endpoints, pois o método HTTP já indica a ação.

Preferível:

```text
GET /users
```

Menos adequado:

```text
GET /getUsers
```

### 5. Principais métodos HTTP

| Método | Finalidade comum | Exemplo |
|---|---|---|
| GET | Consultar dados | `GET /livros` |
| POST | Criar um recurso ou executar uma operação | `POST /livros` |
| PUT | Substituir completamente um recurso | `PUT /livros/10` |
| PATCH | Alterar parcialmente um recurso | `PATCH /livros/10` |
| DELETE | Remover um recurso | `DELETE /livros/10` |

O método `GET` deve ser utilizado para recuperar dados. O `POST` normalmente envia dados para criação de um novo recurso. O `PUT` representa uma substituição completa, enquanto o `PATCH` é usado para alterações parciais. O `DELETE` solicita a remoção de um recurso.

### 6. PUT e PATCH

Considere o recurso:

```json
{
  "id": 10,
  "titulo": "Clean Code",
  "autor": "Robert C. Martin",
  "disponivel": true
}
```

Uma substituição completa com `PUT` poderia ser:

```http
PUT /livros/10
Content-Type: application/json
```

```json
{
  "titulo": "Clean Code",
  "autor": "Robert C. Martin",
  "disponivel": false
}
```

Uma alteração parcial com `PATCH` poderia ser:

```http
PATCH /livros/10
Content-Type: application/json
```

```json
{
  "disponivel": false
}
```

### 7. Idempotência

Uma operação idempotente produz o mesmo efeito no estado do servidor quando repetida várias vezes.

Exemplo:

```http
PUT /usuarios/20
```

Se a mesma requisição for repetida, o recurso continuará com os mesmos dados enviados.

A idempotência é importante quando existem:

- falhas de rede;
- tentativas automáticas;
- timeouts;
- duplicação de requisições;
- processamento distribuído.

É importante diferenciar o resultado da resposta do efeito no servidor. Uma segunda requisição `DELETE` pode retornar outro código de status, mas o recurso já removido não sofre uma nova alteração.

### 8. Códigos de status HTTP

| Código | Significado | Exemplo de uso |
|---|---|---|
| 200 | Sucesso | Consulta ou atualização concluída |
| 201 | Recurso criado | Cadastro realizado |
| 202 | Aceito para processamento | Operação assíncrona |
| 204 | Sucesso sem conteúdo | Exclusão sem corpo de resposta |
| 400 | Requisição inválida | JSON ou parâmetro incorreto |
| 401 | Não autenticado | Token ausente ou inválido |
| 403 | Não autorizado | Usuário sem permissão |
| 404 | Recurso não encontrado | ID inexistente |
| 409 | Conflito | Registro duplicado |
| 422 | Entidade não processável | Dados semanticamente inválidos |
| 500 | Erro interno | Falha inesperada no servidor |

### 9. Statelessness

Em uma arquitetura stateless, cada requisição deve conter as informações necessárias para ser processada.

O servidor não deve depender de uma sequência específica de requisições anteriores para entender a requisição atual.

Por exemplo, um token de autenticação pode ser enviado em cada chamada:

```http
Authorization: Bearer token-do-usuario
```

### 10. JSON e representação de recursos

JSON é um formato frequentemente utilizado para representar recursos em APIs.

Exemplo:

```json
{
  "id": 1,
  "nome": "Maria",
  "email": "maria@example.com"
}
```

O JSON é uma representação. O recurso em si é a entidade identificada pela API, enquanto o JSON é uma forma de apresentar seus dados.

### 11. OpenAPI

OpenAPI é uma especificação para descrever APIs HTTP em um formato padronizado.

Uma descrição OpenAPI pode informar:

- endpoints;
- métodos HTTP;
- parâmetros;
- corpo das requisições;
- respostas;
- códigos de status;
- esquemas de dados;
- mecanismos de autenticação.

Exemplo simplificado:

```yaml
openapi: 3.0.0
info:
  title: API de Livros
  version: 1.0.0

paths:
  /livros:
    get:
      summary: Lista os livros
      responses:
        "200":
          description: Lista retornada com sucesso
```

A partir de uma especificação OpenAPI, é possível gerar documentação, clientes, servidores e testes.

### 12. Modelo de uma API de biblioteca

| Operação | Endpoint | Método |
|---|---|---|
| Listar livros | `/livros` | GET |
| Buscar livro | `/livros/{id}` | GET |
| Criar livro | `/livros` | POST |
| Substituir livro | `/livros/{id}` | PUT |
| Atualizar parte do livro | `/livros/{id}` | PATCH |
| Remover livro | `/livros/{id}` | DELETE |
| Listar empréstimos | `/livros/{id}/emprestimos` | GET |

## Glossário

| Termo | Definição |
|---|---|
| API | Interface que permite a comunicação entre sistemas |
| REST | Estilo arquitetural para sistemas distribuídos |
| HTTP | Protocolo de comunicação baseado em requisição e resposta |
| Recurso | Entidade ou informação manipulada pela API |
| Endpoint | Endereço de acesso a um recurso |
| URI | Identificador utilizado para localizar um recurso |
| Representação | Forma como o estado de um recurso é transmitido |
| JSON | Formato textual usado para representar dados |
| Stateless | Modelo em que cada requisição contém as informações necessárias |
| Idempotência | Propriedade de uma operação que mantém o mesmo efeito quando repetida |
| HATEOAS | Uso de hipermídia para indicar possíveis transições ou ações |
| OpenAPI | Especificação para descrever APIs HTTP |
| Payload | Dados enviados no corpo de uma requisição |
| Header | Metadado enviado na requisição ou resposta |
| Status code | Código que indica o resultado de uma requisição |
| CRUD | Create, Read, Update e Delete |
| Autenticação | Processo de confirmar a identidade de um usuário ou sistema |
| Autorização | Processo de verificar permissões de acesso |

## Prompts reutilizáveis para futuras revisões

### Resumo rápido

```text
Resuma o conteúdo sobre [TEMA] em até 10 tópicos, utilizando somente as fontes carregadas. Destaque definições, exemplos e pontos que costumam gerar confusão.
```

### Explicação por níveis

```text
Explique [CONCEITO] em três níveis:
1. explicação para iniciante;
2. explicação técnica;
3. exemplo aplicado em uma API real.
```

### Comparação

```text
Compare [CONCEITO A] e [CONCEITO B] em uma tabela com definição, finalidade, vantagens, limitações e exemplo de uso.
```

### Identificação de erros

```text
Analise o seguinte endpoint e identifique possíveis problemas de design:

[INSIRA O ENDPOINT]

Explique cada problema e proponha uma alternativa melhor.
```

### Flashcards

```text
Crie 15 flashcards sobre [TEMA]. Em cada flashcard, apresente uma pergunta de um lado e uma resposta curta do outro. Misture conceitos, exemplos e pegadinhas comuns.
```

### Simulado

```text
Crie um simulado com 10 questões sobre [TEMA]. Não mostre o gabarito até que eu responda. Depois, corrija cada questão e explique os erros usando as fontes carregadas.
```

### Revisão espaçada

```text
Monte um plano de revisão sobre [TEMA] para 7 dias. Distribua os conteúdos por dificuldade e inclua perguntas de recuperação ativa em cada dia.
```

## Conclusões

A construção deste caderno mostrou que aprender com Inteligência Artificial exige mais do que solicitar respostas prontas.

A qualidade do estudo melhorou quando foram combinados:

- fontes confiáveis;
- perguntas específicas;
- comparação entre respostas;
- validação das informações;
- registro das dificuldades;
- revisão ativa;
- organização do conhecimento.

O principal aprendizado técnico foi compreender que REST é um estilo arquitetural, enquanto HTTP é um protocolo de comunicação. Também foi possível entender a função dos principais métodos HTTP, a importância da idempotência, a diferença entre PUT e PATCH e o papel do OpenAPI na documentação de APIs.

## Evidências do projeto

Adicione nesta seção:

- captura de tela do NotebookLM com as fontes carregadas;
- captura de tela dos prompts utilizados;
- captura de tela de uma resposta referenciada;
- link para o repositório;
- link para o caderno, caso esteja disponível publicamente.

## Autor

Desenvolvido por **Antonio C. Leite Jr**.

Projeto criado para fins educacionais como parte de um desafio da DIO.
