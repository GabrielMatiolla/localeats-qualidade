# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## 1. Identificação

**Turma:** Qualidade de Software - Terça/Noite - POA

### Integrantes

| Nome                   | Usuário no GitHub |
| ---------------------- | ----------------- |
| Gabriel Tadeu Matiolla | @GabrielMatiolla  |
| Thiago Figueiredo      | @ThiagoF1703      |
| Henrique Mello         | @eiHenriqueMello  |

**Elemento de Competência:** Planejar e projetar testes selecionando técnicas adequadas.

**Aplicação:** https://local-eats-unisenac.vercel.app/

---

# Tarefa 1: Planejamento dos testes

## 1.1 Objetivo dos testes

Planejar testes para verificar se as funcionalidades selecionadas do LocalEats apresentam os comportamentos esperados em situações válidas e inválidas, considerando os principais riscos relacionados a cada funcionalidade.

O planejamento busca selecionar técnicas adequadas para identificar possíveis falhas e estabelecer casos de teste com entradas, condições, passos e resultados esperados claramente definidos.

---

## 1.2 Escopo

As funcionalidades selecionadas para este ciclo de testes são:

| Integrante             | Funcionalidade incluída                  | O que será verificado                                                                                              |
| ---------------------- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Gabriel Tadeu Matiolla | Pesquisar restaurantes por especialidade | Verificar o comportamento da pesquisa quando existem restaurantes correspondentes e quando não existem resultados. |
| Thiago Figueiredo      | Fazer pedido                             | Verificar o comportamento da realização de um pedido com produto no carrinho e com o carrinho vazio.               |
| Henrique Mello         | Criar conta                              | Verificar o comportamento do cadastro com um e-mail ainda não cadastrado e com um e-mail já cadastrado.            |

### Funcionalidade não incluída

| Funcionalidade não incluída           | Justificativa                                                                                                              |
| ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Favoritar e desfavoritar restaurantes | Não faz parte das funcionalidades selecionadas pelos integrantes neste ciclo e não está relacionada aos riscos analisados. |

As demais funcionalidades do LocalEats, como entrar no sistema, explorar restaurantes e consultar pedidos, também não serão avaliadas neste ciclo.

---

## 1.3 Abordagem

| Item              | Decisão da equipe                                   | Justificativa                                                                                                                                                                                                       |
| ----------------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Níveis de teste   | Sistema                                             | Os testes serão planejados considerando a interação do usuário com a aplicação e o comportamento das funcionalidades como um todo.                                                                                  |
| Tipos de teste    | Funcional                                           | O objetivo é verificar se as funcionalidades selecionadas apresentam os comportamentos esperados para diferentes entradas e condições.                                                                              |
| Perspectiva       | Caixa-preta                                         | Os casos serão definidos a partir das entradas fornecidas pelo usuário e dos resultados esperados, sem considerar a implementação interna da aplicação.                                                             |
| Técnicas de teste | Particionamento de Equivalência e Tabela de Decisão | O Particionamento de Equivalência é adequado para dividir entradas e situações em classes de comportamento. A Tabela de Decisão é adequada para relacionar condições de cadastro com as ações esperadas do sistema. |

### Justificativa das técnicas

O **Particionamento de Equivalência** será utilizado para dividir as entradas e situações em classes que representam comportamentos válidos e inválidos. Dessa forma, é possível selecionar casos representativos para cada classe sem precisar testar todas as possibilidades.

A **Tabela de Decisão** será utilizada na funcionalidade de criação de conta para relacionar as condições do cadastro com as ações esperadas do sistema, principalmente considerando se o e-mail informado já está cadastrado.

---

## 1.4 Ambiente e responsabilidades

| Item                                      | Definição                                                                                                                                                  |
| ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ambiente necessário                       | Aplicação LocalEats disponível, navegador Google Chrome, computador ou notebook com acesso à internet e dados de teste definidos para cada funcionalidade. |
| Responsáveis pelo planejamento            | Gabriel Tadeu Matiolla: pesquisa de restaurantes por especialidade; Thiago Figueiredo: realização de pedidos; Henrique Mello: criação de conta.            |
| Responsáveis pela especificação dos casos | Cada integrante será responsável pela especificação dos casos relacionados à sua própria funcionalidade.                                                   |
| Responsáveis pela futura execução         | Cada integrante será responsável pela futura execução dos casos relacionados à sua funcionalidade, com revisão da equipe.                                  |

**Aplicação:** https://local-eats-unisenac.vercel.app/

---

## 1.5 Critérios

| Critério  | Definição da equipe                                                                                                                                                                                                                              |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Entrada   | Aplicação disponível, funcionalidades selecionadas identificadas, riscos definidos, técnicas escolhidas, casos de teste documentados e dados necessários disponíveis.                                                                            |
| Saída     | Todos os riscos selecionados possuem pelo menos um caso de teste relacionado, todos os casos possuem técnica, pré-condição, dados de entrada, passos e resultado esperado, e a matriz de rastreabilidade está preenchida e revisada pela equipe. |
| Suspensão | A aplicação estiver indisponível, uma funcionalidade necessária para o teste não estiver acessível, não houver dados necessários para realizar o caso ou uma alteração na aplicação tornar o caso de teste incompatível com a versão disponível. |

---

# Tarefa 2: Riscos e técnicas de teste

## 2.1 Análise dos riscos

| ID  | Integrante             | Funcionalidade                           | Risco                                                                                                                              | Consequência                                                                                                         | Probabilidade | Impacto | Prioridade | Justificativa                                                                                                                                                                                                                                   |
| --- | ---------------------- | ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | ------------- | ------- | ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R01 | Gabriel Tadeu Matiolla | Pesquisar restaurantes por especialidade | A pesquisa pode não retornar corretamente os restaurantes correspondentes ou não tratar adequadamente uma pesquisa sem resultados. | O usuário pode não encontrar o restaurante desejado ou pode não compreender que a pesquisa não encontrou resultados. | Média         | Média   | Média      | A pesquisa é importante para localizar restaurantes. Uma falha pode prejudicar diretamente o uso dessa funcionalidade.                                                                                                                          |
| R02 | Thiago Figueiredo      | Fazer pedido                             | O sistema pode impedir a finalização de um pedido quando existe pelo menos um produto no carrinho.                                 | O usuário não consegue concluir o pedido.                                                                            | Média         | Alta    | Alta       | A finalização é uma etapa essencial da realização do pedido. Se ela não funcionar, o usuário não consegue concluir a operação.                                                                                                                  |
| R03 | Thiago Figueiredo      | Fazer pedido                             | O sistema pode permitir a tentativa de finalização de um pedido com o carrinho vazio.                                              | O usuário pode tentar finalizar um pedido sem nenhum produto no carrinho.                                            | Baixa         | Alta    | Média      | Trata-se de uma condição inválida que deve ser tratada pelo sistema. A probabilidade foi considerada baixa porque, na exploração anterior, a opção de finalização não apareceu quando o carrinho estava vazio.                                  |
| R04 | Henrique Mello         | Criar conta                              | O sistema pode permitir o cadastro de uma nova conta utilizando um e-mail que já está cadastrado.                                  | O sistema pode aceitar um cadastro que deveria ser bloqueado.                                                        | Baixa         | Alta    | Média      | A probabilidade foi considerada baixa porque, na exploração anterior, o sistema identificou o e-mail já cadastrado e apresentou uma mensagem informando a situação. O risco deve ser mantido para verificar se esse comportamento é preservado. |

---

## 2.2 Aplicação da técnica

### Integrante responsável

**Nome:** Gabriel Tadeu Matiolla

**Funcionalidade:** Pesquisar restaurantes por especialidade

**Risco relacionado:** R01

**Técnica escolhida:** Particionamento de Equivalência

### Por que a técnica foi escolhida?

O Particionamento de Equivalência foi escolhido porque permite dividir as pesquisas em classes de entradas com comportamentos esperados diferentes, considerando uma especialidade que possui restaurantes correspondentes e uma especialidade sem resultados.

### Aplicação da técnica

| Classe               | Situação                                                           | Exemplo           |
| -------------------- | ------------------------------------------------------------------ | ----------------- |
| Classe válida        | Especialidade que possui restaurantes correspondentes              | "Italiana"        |
| Classe sem resultado | Especialidade para a qual não existem restaurantes correspondentes | "Comida de Marte" |

### Casos derivados

* **CT01:** pesquisar por uma especialidade existente.
* **CT02:** pesquisar por uma especialidade sem restaurantes correspondentes.

---

### Integrante responsável

**Nome:** Thiago Figueiredo

**Funcionalidade:** Fazer pedido

**Riscos relacionados:**

* **R02:** O sistema pode impedir a finalização de um pedido quando existe pelo menos um produto no carrinho.
* **R03:** O sistema pode permitir a tentativa de finalização de um pedido com o carrinho vazio.

**Técnica escolhida:** Particionamento de Equivalência

### Por que a técnica foi escolhida?

O Particionamento de Equivalência foi escolhido porque permite dividir as situações do carrinho em classes válidas e inválidas, considerando a existência ou ausência de produtos antes da tentativa de finalização do pedido.

### Aplicação da técnica

| Classe          | Situação                               |
| --------------- | -------------------------------------- |
| Classe válida   | Carrinho possui pelo menos um produto. |
| Classe inválida | Carrinho não possui nenhum produto.    |

### Casos derivados

* **CT03:** finalizar pedido com produto no carrinho.
* **CT04:** tentar finalizar pedido com o carrinho vazio.

---

### Integrante responsável

**Nome:** Henrique Mello

**Funcionalidade:** Criar conta

**Risco relacionado:** R04

**Técnica escolhida:** Tabela de Decisão

### Por que a técnica foi escolhida?

A Tabela de Decisão foi escolhida porque permite relacionar as condições do cadastro com as ações esperadas do sistema. Neste caso, a principal condição analisada é se o e-mail informado já está cadastrado.

### Aplicação da técnica

| Condição / Ação                             | CT05    | CT06    |
| ------------------------------------------- | ------- | ------- |
| Dados de cadastro válidos                   | Sim     | Sim     |
| E-mail já cadastrado                        | Não     | Sim     |
| **Permitir criação da conta**               | **Sim** | **Não** |
| **Exibir mensagem de e-mail já cadastrado** | **Não** | **Sim** |

### Casos derivados

* **CT05:** criar conta com e-mail ainda não cadastrado.
* **CT06:** tentar criar conta com e-mail já cadastrado.

---

# Tarefa 3: Casos de teste e rastreabilidade

## 3.1 Especificação dos casos de teste

## CT01 — Pesquisar restaurante por especialidade existente

**Integrante responsável:** Gabriel Tadeu Matiolla

**Funcionalidade:** Pesquisar restaurantes por especialidade

**Risco relacionado:** R01

**Técnica utilizada:** Particionamento de Equivalência

**Pré-condição:** A aplicação está disponível e o usuário consegue acessar a funcionalidade de pesquisa por especialidade.

**Dados de entrada:** Especialidade "Italiana".

### Passos

1. Acessar a aplicação LocalEats.
2. Acessar a funcionalidade de pesquisa por especialidade.
3. Informar ou selecionar a especialidade "Italiana".
4. Realizar a pesquisa.

### Resultado esperado

O sistema deve apresentar os restaurantes correspondentes à especialidade pesquisada.

---

## CT02 — Pesquisar especialidade sem restaurantes correspondentes

**Integrante responsável:** Gabriel Tadeu Matiolla

**Funcionalidade:** Pesquisar restaurantes por especialidade

**Risco relacionado:** R01

**Técnica utilizada:** Particionamento de Equivalência

**Pré-condição:** A aplicação está disponível e o usuário consegue acessar a funcionalidade de pesquisa por especialidade.

**Dados de entrada:** Especialidade "Comida de Marte".

### Passos

1. Acessar a aplicação LocalEats.
2. Acessar a funcionalidade de pesquisa por especialidade.
3. Informar ou selecionar "Comida de Marte".
4. Realizar a pesquisa.

### Resultado esperado

O sistema deve informar que não existem restaurantes correspondentes à pesquisa, apresentando uma mensagem clara de que nenhum restaurante foi encontrado.

---

## CT03 — Finalizar pedido com produto no carrinho

**Integrante responsável:** Thiago Figueiredo

**Funcionalidade:** Fazer pedido

**Risco relacionado:** R02

**Técnica utilizada:** Particionamento de Equivalência

**Pré-condição:** O usuário está na aplicação e existe um restaurante com pelo menos um produto disponível.

**Dados de entrada:** Um produto disponível no restaurante.

### Passos

1. Acessar um restaurante.
2. Selecionar um produto.
3. Adicionar o produto ao carrinho.
4. Acessar o carrinho.
5. Tentar finalizar o pedido.

### Resultado esperado

O produto deve ser adicionado ao carrinho, o total deve ser atualizado e o sistema deve permitir a finalização do pedido.

---

## CT04 — Tentar finalizar pedido com carrinho vazio

**Integrante responsável:** Thiago Figueiredo

**Funcionalidade:** Fazer pedido

**Risco relacionado:** R03

**Técnica utilizada:** Particionamento de Equivalência

**Pré-condição:** O carrinho não possui nenhum produto.

**Dados de entrada:** Nenhum produto.

### Passos

1. Acessar o carrinho sem adicionar produtos.
2. Verificar as opções disponíveis para finalização do pedido.
3. Tentar realizar a finalização do pedido, caso a opção esteja disponível.

### Resultado esperado

O sistema não deve permitir a finalização de um pedido quando o carrinho estiver vazio. A opção de finalizar o pedido não deve ser disponibilizada enquanto não houver nenhum produto no carrinho.

---

## CT05 — Criar conta com e-mail ainda não cadastrado

**Integrante responsável:** Henrique Mello

**Funcionalidade:** Criar conta

**Risco relacionado:** R04

**Técnica utilizada:** Tabela de Decisão

**Pré-condição:** Não existe uma conta cadastrada utilizando o e-mail informado.

**Dados de entrada:**

* Nome completo válido;
* E-mail ainda não cadastrado;
* Senha válida.

### Passos

1. Acessar a opção de criação de conta.
2. Informar o nome completo.
3. Informar um e-mail ainda não cadastrado.
4. Informar uma senha válida.
5. Confirmar o cadastro.

### Resultado esperado

O sistema deve permitir a criação da conta utilizando os dados informados.

---

## CT06 — Tentar criar conta com e-mail já cadastrado

**Integrante responsável:** Henrique Mello

**Funcionalidade:** Criar conta

**Risco relacionado:** R04

**Técnica utilizada:** Tabela de Decisão

**Pré-condição:** Já existe uma conta cadastrada utilizando o e-mail informado.

**Dados de entrada:**

* Nome completo válido;
* E-mail já cadastrado;
* Senha válida.

### Passos

1. Acessar a opção de criação de conta.
2. Informar o nome completo.
3. Informar um e-mail que já esteja cadastrado.
4. Informar uma senha válida.
5. Confirmar o cadastro.

### Resultado esperado

O sistema deve impedir a criação de uma nova conta utilizando um e-mail já cadastrado e apresentar uma mensagem informando que o e-mail já está cadastrado.

---

## 3.2 Matriz de rastreabilidade

| Integrante             | Funcionalidade                           | Risco ou requisito                                                                                                   | Técnica utilizada               | Casos de teste |
| ---------------------- | ---------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | ------------------------------- | -------------- |
| Gabriel Tadeu Matiolla | Pesquisar restaurantes por especialidade | R01: A pesquisa pode não retornar corretamente os restaurantes ou não tratar adequadamente pesquisas sem resultados. | Particionamento de Equivalência | CT01 e CT02    |
| Thiago Figueiredo      | Fazer pedido                             | R02: O sistema pode impedir a finalização de um pedido quando existe pelo menos um produto no carrinho.              | Particionamento de Equivalência | CT03           |
| Thiago Figueiredo      | Fazer pedido                             | R03: O sistema pode permitir a tentativa de finalização de um pedido com o carrinho vazio.                           | Particionamento de Equivalência | CT04           |
| Henrique Mello         | Criar conta                              | R04: O sistema pode permitir cadastro com e-mail já registrado.                                                      | Tabela de Decisão               | CT05 e CT06    |

A matriz demonstra a relação entre cada funcionalidade analisada, seus riscos, as técnicas utilizadas e os respectivos casos de teste. Dessa forma, todos os riscos identificados possuem pelo menos um caso de teste relacionado.

---

# Uso de inteligência artificial

**Ferramenta utilizada:** Gemini

**Como foi utilizada:** A ferramenta foi utilizada como apoio na organização da estratégia de testes, identificação de riscos, escolha das técnicas de teste e estruturação dos casos de teste.

**Uma sugestão que precisou ser alterada ou rejeitada:** Algumas sugestões apresentadas pela ferramenta envolviam situações que não estavam relacionadas diretamente às funcionalidades selecionadas pela equipe, como testes de entrada de scripts ou URLs. Essas sugestões foram rejeitadas porque estavam fora do escopo definido para esta atividade.

**Como as respostas foram verificadas:** 

A equipe também revisou a rastreabilidade entre funcionalidades, riscos, técnicas e casos de teste antes de incluir as informações no documento.
