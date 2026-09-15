## Engenharia de prompts e cicatrizes

Durante os testes, foi possível observar que a qualidade das respostas dependia bastante do nível de detalhamento do prompt.

### Teste 1 — Prompt genérico

Explique APIs REST.

#### Resultado

A resposta foi ampla, mas apresentou muitos conceitos ao mesmo tempo e não deixou claro quais informações vieram das fontes.

#### Problema identificado

- Escopo muito amplo.
- Ausência de nível de conhecimento do estudante.
- Falta de exigência de referências.
- Falta de formato definido para a resposta.

### Teste 2 — Prompt com contexto

Explique APIs REST para um estudante iniciante de desenvolvimento web. Organize a resposta em definição, funcionamento, exemplos e conceitos relacionados.

#### Resultado

A resposta ficou mais organizada e acessível, porém ainda apresentou pouca comparação entre REST e HTTP.

### Teste 3 — Prompt com restrições e fontes

Explique APIs REST para um estudante iniciante. Organize a resposta nas seções definição, funcionamento, recursos, endpoints, métodos HTTP e códigos de status. Use somente as fontes carregadas no NotebookLM e indique qual fonte apoia cada parte da explicação. Caso uma informação não esteja nas fontes, informe isso explicitamente.

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

Também existe uma segunda seção, chamada **“Perguntas estratégicas utilizadas”**, que reúne os prompts aplicados ao estudo:

## Perguntas estratégicas utilizadas

### Prompt 1 — Visão geral

Explique o que é uma API REST para uma pessoa que conhece lógica de programação, mas ainda não trabalha com desenvolvimento web. Use uma explicação progressiva, começando pelos conceitos mais simples e avançando até recursos, endpoints e métodos HTTP. Utilize somente as fontes fornecidas.

### Prompt 2 — Comparação entre conceitos

Compare REST, HTTP e API. Para cada conceito, apresente:
1. definição;
2. finalidade;
3. relação com os demais conceitos;
4. exemplo prático;
5. erro comum de interpretação.
Utilize referências às fontes usadas.

### Prompt 3 — Métodos HTTP

Crie uma tabela com os métodos GET, POST, PUT, PATCH e DELETE. Informe:
- finalidade;
- exemplo de endpoint;
- se normalmente é idempotente;
- possível código de resposta;
- erro comum de uso.
Não invente informações que não estejam nas fontes.

### Prompt 4 — Estudo baseado em cenário

Considere uma API de biblioteca com os recursos livros e usuários. Proponha endpoints REST para:
- listar livros;
- buscar um livro;
- cadastrar um livro;
- alterar completamente um livro;
- alterar parcialmente um livro;
- remover um livro.

Explique por que cada método HTTP foi escolhido.

### Prompt 5 — Revisão crítica

Analise a afirmação: "Toda API que utiliza HTTP e JSON é automaticamente RESTful".

Diga se a afirmação está correta ou incorreta, explique o motivo e apresente um exemplo de API que utiliza HTTP, mas não segue completamente os princípios de REST.

## Prompts reutilizáveis para futuras revisões

### Resumo rápido

Resuma o conteúdo sobre [TEMA] em até 10 tópicos, utilizando somente as fontes carregadas. Destaque definições, exemplos e pontos que costumam gerar confusão.

### Explicação por níveis

Explique [CONCEITO] em três níveis:
1. explicação para iniciante;
2. explicação técnica;
3. exemplo aplicado em uma API real.

### Comparação

Compare [CONCEITO A] e [CONCEITO B] em uma tabela com definição, finalidade, vantagens, limitações e exemplo de uso.

### Flashcards

Crie 15 flashcards sobre [TEMA]. Em cada flashcard, apresente uma pergunta de um lado e uma resposta curta do outro. Misture conceitos, exemplos e pegadinhas comuns.

### Simulado

Crie um simulado com 10 questões sobre [TEMA]. Não mostre o gabarito até que eu responda. Depois, corrija cada questão e explique os erros usando as fontes carregadas.
