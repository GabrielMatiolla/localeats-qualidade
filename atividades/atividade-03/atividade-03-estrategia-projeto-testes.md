# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## Identificação

**Turma:** Qualidade de Software - Terça/Noite - POA

### Integrantes

| Nome                   | Usuário no GitHub |
| :--------------------- | :---------------- |
| Gabriel Tadeu Matiolla | @GabrielMatiolla  |
| Thiago Figueiredo      | @ThiagoF1703      |
| Henrique Mello         | @eiHenriqueMello  |

**Aplicação:** https://local-eats-unisenac.vercel.app/

---

# Tarefa 1: Estratégia de testes

## 1.1 Objetivo

Planejar testes para verificar se as funcionalidades selecionadas do LocalEats apresentam os comportamentos esperados em situações válidas e inválidas, considerando os principais riscos relacionados a cada funcionalidade.

O planejamento busca selecionar técnicas adequadas para identificar possíveis falhas e estabelecer casos de teste com entradas, condições e resultados esperados claramente definidos.

---

## 1.2 Escopo

As funcionalidades selecionadas para este ciclo de testes são:

| Integrante             | Funcionalidade                           | Objetivo do teste                                                                                                  |
| :--------------------- | :--------------------------------------- | :----------------------------------------------------------------------------------------------------------------- |
| Gabriel Tadeu Matiolla | Pesquisar restaurantes por especialidade | Verificar o comportamento da pesquisa quando existem restaurantes correspondentes e quando não existem resultados. |
| Thiago Figueiredo      | Fazer pedido                             | Verificar o comportamento da realização de um pedido com produto no carrinho e com o carrinho vazio.               |
| Henrique Mello         | Criar conta                              | Verificar o comportamento do cadastro com um e-mail ainda não cadastrado e com um e-mail já cadastrado.            |

### Fora do escopo

Não serão avaliadas neste ciclo as demais funcionalidades do LocalEats, como entrar no sistema, explorar restaurantes, favoritar ou desfavoritar restaurantes e consultar pedidos.

---

## 1.3 Abordagem de testes

### Nível de teste

**Teste de sistema:** os testes serão planejados considerando a interação do usuário com a aplicação e o comportamento das funcionalidades como um todo.

### Tipo de teste

**Teste funcional:** serão avaliadas as funcionalidades selecionadas de acordo com os comportamentos esperados para diferentes entradas e condições.

### Perspectiva

**Teste de caixa-preta:** os casos serão definidos a partir das entradas fornecidas pelo usuário e dos resultados esperados, sem considerar a implementação interna da aplicação.

### Técnicas utilizadas

* **Particionamento de Equivalência**
* **Tabela de Decisão**

### Justificativa das técnicas

O **Particionamento de Equivalência** será utilizado para dividir as entradas em classes que representam comportamentos válidos e inválidos. Dessa forma, é possível selecionar casos representativos para cada classe.

A **Tabela de Decisão** será utilizada na funcionalidade de criação de conta para relacionar diferentes condições de entrada, principalmente a situação do e-mail utilizado no cadastro, e determinar o comportamento esperado do sistema.

---

## 1.4 Ambiente e responsabilidades

### Ambiente

* Navegador Google Chrome;
* Aplicação LocalEats;
* Conexão com a internet;
* Dados de teste definidos para cada funcionalidade.

**Aplicação:** https://local-eats-unisenac.vercel.app/

### Responsabilidades

| Integrante             | Responsabilidade                                                                       |
| :--------------------- | :------------------------------------------------------------------------------------- |
| Gabriel Tadeu Matiolla | Planejar os testes relacionados à pesquisa de restaurantes por especialidade.          |
| Thiago Figueiredo      | Planejar os testes relacionados à realização de pedidos.                               |
| Henrique Mello         | Planejar os testes relacionados à criação de contas.                                   |
| Equipe                 | Revisar os riscos, técnicas e casos de teste e verificar a rastreabilidade entre eles. |

---

## 1.5 Critérios de entrada

Os testes poderão ser considerados prontos para execução quando:

* A aplicação estiver disponível;
* As funcionalidades selecionadas estiverem identificadas;
* Os riscos relacionados às funcionalidades estiverem definidos;
* As técnicas de teste estiverem selecionadas;
* Os casos de teste estiverem documentados;
* Os dados necessários para os testes estiverem definidos.

---

## 1.6 Critérios de saída

O planejamento será considerado concluído quando:

* Todas as funcionalidades selecionadas possuírem pelo menos um risco identificado;
* Todos os riscos selecionados estiverem relacionados a casos de teste;
* Cada caso de teste possuir técnica, pré-condição, dados de entrada, passos e resultado esperado;
* A matriz de rastreabilidade estiver preenchida;
* Os casos de teste estiverem revisados pela equipe.

---

## 1.7 Critérios de suspensão

O teste poderá ser suspenso caso:

* A aplicação esteja indisponível;
* Uma funcionalidade necessária para o teste não esteja acessível;
* Não seja possível fornecer os dados necessários para realizar o teste;
* Uma alteração na aplicação torne o caso de teste incompatível com a versão disponível.

---

# Tarefa 2: Análise de riscos e técnicas

## 2.1 Riscos identificados

| ID  | Integrante             | Funcionalidade                           | Risco                                                                                                                              | Consequência                                                                                                         | Probabilidade | Impacto | Prioridade |
| :-- | :--------------------- | :--------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------- | :------------ | :------ | :--------- |
| R01 | Gabriel Tadeu Matiolla | Pesquisar restaurantes por especialidade | A pesquisa pode não retornar corretamente os restaurantes correspondentes ou não tratar adequadamente uma pesquisa sem resultados. | O usuário pode não encontrar o restaurante desejado ou pode não compreender que a pesquisa não encontrou resultados. | Média         | Média   | Média      |
| R02 | Thiago Figueiredo      | Fazer pedido                             | O sistema pode impedir a finalização de um pedido quando existe pelo menos um produto no carrinho.                                 | O usuário não consegue concluir o pedido.                                                                            | Média         | Alta    | Alta       |
| R03 | Thiago Figueiredo      | Fazer pedido                             | O sistema pode permitir a tentativa de finalização de um pedido com o carrinho vazio.                                              | O usuário pode tentar finalizar um pedido sem nenhum produto no carrinho.                                            | Baixa         | Alta    | Média      |
| R04 | Henrique Mello         | Criar conta                              | O sistema pode permitir o cadastro de uma nova conta utilizando um e-mail que já está cadastrado.                                  | Podem ser criadas contas duplicadas utilizando o mesmo e-mail.                                                       | Baixa         | Alta    | Média      |

---

## 2.2 Relação entre riscos, técnicas e casos de teste

### Gabriel Tadeu Matiolla

**Funcionalidade:** Pesquisar restaurantes por especialidade

**Risco relacionado:** R01

**Técnica escolhida:** Particionamento de Equivalência

### Justificativa

O Particionamento de Equivalência foi escolhido porque permite dividir as pesquisas em classes de entradas com comportamentos esperados diferentes.

### Classes de equivalência

* **Classe válida:** especialidade que possui restaurantes correspondentes na aplicação.
* **Classe sem resultado:** especialidade para a qual não existem restaurantes correspondentes.

### Casos derivados

* **CT01:** pesquisa por uma especialidade existente.
* **CT02:** pesquisa por uma especialidade sem restaurantes correspondentes.

---

### Thiago Figueiredo

**Funcionalidade:** Fazer pedido

**Riscos relacionados:**

* **R02:** O sistema pode impedir a finalização de um pedido quando existe pelo menos um produto no carrinho.
* **R03:** O sistema pode permitir a tentativa de finalização de um pedido com o carrinho vazio.

**Técnica escolhida:** Particionamento de Equivalência

### Justificativa

O Particionamento de Equivalência foi escolhido porque permite dividir as situações do carrinho em classes válidas e inválidas, considerando a existência ou ausência de produtos antes da tentativa de finalização do pedido.

### Classes de equivalência

* **Classe válida:** carrinho possui pelo menos um produto.
* **Classe inválida:** carrinho não possui nenhum produto.

### Casos derivados

* **CT03:** finalizar pedido com produto no carrinho.
* **CT04:** tentar finalizar pedido com o carrinho vazio.

---

### Henrique Mello

**Funcionalidade:** Criar conta

**Risco relacionado:** R04

**Técnica escolhida:** Tabela de Decisão

### Justificativa

A Tabela de Decisão foi escolhida porque permite relacionar as condições do cadastro com as ações esperadas do sistema. Neste caso, a principal condição analisada é se o e-mail informado já está cadastrado.

### Tabela de decisão

| Condição / Ação                             |   CT05  |   CT06  |
| :------------------------------------------ | :-----: | :-----: |
| Dados de cadastro válidos                   |   Sim   |   Sim   |
| E-mail já cadastrado                        |   Não   |   Sim   |
| **Permitir criação da conta**               | **Sim** | **Não** |
| **Exibir mensagem de e-mail já cadastrado** | **Não** | **Sim** |

### Casos derivados

* **CT05:** criar conta com e-mail ainda não cadastrado.
* **CT06:** tentar criar conta com e-mail já cadastrado.

---

# Tarefa 3: Projeto dos casos de teste

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

# Tarefa 4: Matriz de rastreabilidade

| Integrante             | Funcionalidade                           | Risco ou requisito                                                                                                   | Técnica utilizada               | Casos de teste |
| :--------------------- | :--------------------------------------- | :------------------------------------------------------------------------------------------------------------------- | :------------------------------ | :------------- |
| Gabriel Tadeu Matiolla | Pesquisar restaurantes por especialidade | R01: A pesquisa pode não retornar corretamente os restaurantes ou não tratar adequadamente pesquisas sem resultados. | Particionamento de Equivalência | CT01 e CT02    |
| Thiago Figueiredo      | Fazer pedido                             | R02: O sistema pode impedir a finalização de um pedido quando existe pelo menos um produto no carrinho.              | Particionamento de Equivalência | CT03           |
| Thiago Figueiredo      | Fazer pedido                             | R03: O sistema pode permitir a tentativa de finalização de um pedido com o carrinho vazio.                           | Particionamento de Equivalência | CT04           |
| Henrique Mello         | Criar conta                              | R04: O sistema pode permitir cadastro com e-mail já registrado.                                                      | Tabela de Decisão               | CT05 e CT06    |

---

# Uso de inteligência artificial

**Ferramenta utilizada:** 

**Como foi utilizada:** 

**Como as respostas foram verificadas:
