# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## Identificação da equipe

| Integrante             | GitHub           |
| :--------------------- | :--------------- |
| Gabriel Tadeu Matiolla | @GabrielMatiolla |
| Thiago Figueiredo      | @ThiagoF1703     |
| Henrique Mello         | @eiHenriqueMello |

**Data:** 18/09/2026
**Aplicação:** [LocalEats](https://local-eats-unisenac.vercel.app/)

---

# 1. Estratégia de Testes

## 1.1 Objetivo dos testes

Verificar se as principais funcionalidades selecionadas do LocalEats apresentam os comportamentos esperados em situações válidas e inválidas, identificando riscos que possam prejudicar a utilização do sistema e planejando casos de teste adequados para cada situação.

---

## 1.2 Escopo

As funcionalidades selecionadas para este ciclo de testes são:

| Integrante             | Funcionalidade                           | O que será verificado                                                                                                                         |
| :--------------------- | :--------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------- |
| Gabriel Tadeu Matiolla | Pesquisar restaurantes por especialidade | Verificar a pesquisa por uma especialidade existente e o comportamento quando não existem restaurantes correspondentes.                       |
| Thiago Figueiredo      | Fazer pedido                             | Verificar a adição de produtos ao carrinho, a atualização do total e o comportamento da finalização do pedido com e sem produtos no carrinho. |
| Henrique Mello         | Criar conta                              | Verificar a criação de uma conta com dados válidos e o comportamento quando o e-mail informado já está cadastrado.                            |

### Fora do escopo

Neste ciclo não serão avaliadas as demais funcionalidades da aplicação, como consultar pedidos, favoritar restaurantes ou pesquisar por localização.

---

## 1.3 Abordagem de testes

### Nível de teste

**Teste de sistema:** as funcionalidades serão analisadas considerando o comportamento da aplicação como um todo, a partir da interação do usuário com a interface.

### Tipo de teste

**Teste funcional:** serão verificadas as funções disponibilizadas pela aplicação e seus comportamentos esperados.

### Perspectiva

**Caixa-preta:** os testes serão planejados com base nas entradas fornecidas pelo usuário e nos resultados esperados, sem considerar a implementação interna do sistema.

### Técnicas utilizadas

* **Particionamento de Equivalência**
* **Tabela de Decisão**

### Justificativa

O **Particionamento de Equivalência** será utilizado para dividir as entradas em classes válidas e inválidas, reduzindo a quantidade de casos necessários sem deixar de representar situações diferentes de uso.

A **Tabela de Decisão** será utilizada para verificar diferentes combinações de condições no processo de criação de uma conta, principalmente considerando se os dados informados são válidos e se o e-mail já está cadastrado.

---

## 1.4 Ambiente e responsabilidades

### Ambiente

* Navegador Google Chrome;
* Aplicação LocalEats disponível em: https://local-eats-unisenac.vercel.app/;
* Conexão com a internet;
* Dados de teste definidos para cada funcionalidade.

### Responsabilidades

| Integrante             | Responsabilidade                                                                                                           |
| :--------------------- | :------------------------------------------------------------------------------------------------------------------------- |
| Gabriel Tadeu Matiolla | Planejar os testes relacionados à pesquisa de restaurantes por especialidade.                                              |
| Thiago Figueiredo      | Planejar os testes relacionados à realização de pedidos.                                                                   |
| Henrique Mello         | Planejar os testes relacionados à criação de contas.                                                                       |
| Equipe                 | Revisar os casos de teste, verificar a coerência dos resultados esperados e manter a rastreabilidade entre riscos e casos. |

---

## 1.5 Critérios de entrada, saída e suspensão

### Critérios de entrada

* Aplicação LocalEats disponível para acesso;
* Funcionalidades selecionadas identificadas;
* Riscos definidos;
* Técnicas de teste selecionadas;
* Dados de entrada disponíveis para a elaboração dos casos.

### Critérios de saída

* Todos os riscos selecionados relacionados às funcionalidades devem possuir casos de teste;
* Todos os casos devem possuir técnica de teste definida;
* Todos os casos devem apresentar resultados esperados observáveis;
* A matriz de rastreabilidade deve relacionar funcionalidades, riscos, técnicas e casos de teste.

### Critérios de suspensão

O planejamento ou execução dos testes poderá ser suspenso caso:

* A aplicação esteja indisponível;
* Uma funcionalidade necessária para o teste não esteja acessível;
* Não seja possível obter os dados necessários para realizar o teste;
* Alguma alteração na aplicação impeça a utilização dos casos planejados.

---

# 2. Análise de Riscos e Técnicas

## 2.1 Riscos identificados

| ID  | Integrante             | Funcionalidade                           | Risco                                                                                                                              | Consequência                                                                                       | Probabilidade | Impacto | Prioridade |
| :-- | :--------------------- | :--------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------- | :------------ | :------ | :--------- |
| R01 | Gabriel Tadeu Matiolla | Pesquisar restaurantes por especialidade | A pesquisa pode não retornar corretamente os restaurantes correspondentes ou não tratar adequadamente uma pesquisa sem resultados. | O usuário pode não encontrar o restaurante desejado ou não compreender que não existem resultados. | Média         | Média   | Média      |
| R02 | Thiago Figueiredo      | Fazer pedido                             | O sistema pode impedir a finalização de um pedido quando existe pelo menos um produto no carrinho.                                 | O usuário não consegue concluir o pedido.                                                          | Média         | Alta    | Alta       |
| R03 | Thiago Figueiredo      | Fazer pedido                             | O sistema pode permitir a tentativa de finalização de um pedido com o carrinho vazio.                                              | O sistema pode permitir uma operação inválida ou gerar inconsistência no pedido.                   | Baixa         | Alta    | Média      |
| R04 | Henrique Mello         | Criar conta                              | O sistema pode permitir o cadastro de uma nova conta utilizando um e-mail que já está cadastrado.                                  | Podem ocorrer contas duplicadas ou inconsistências nos dados dos usuários.                         | Baixa         | Alta    | Média      |

---

## 2.2 Aplicação das técnicas

### Gabriel Tadeu Matiolla

**Funcionalidade:** Pesquisar restaurantes por especialidade

**Risco relacionado:** R01

**Técnica escolhida:** Particionamento de Equivalência

**Por que a técnica foi escolhida?**

A técnica foi escolhida porque permite dividir as pesquisas em classes de entradas válidas e inválidas, considerando uma especialidade que possui restaurantes cadastrados e uma especialidade que não possui resultados.

**Aplicação da técnica:**

* **Classe válida:** especialidade existente na aplicação, como "Italiana".
* **Classe inválida:** especialidade para a qual não existem restaurantes correspondentes, como "Comida de Marte".

**Casos derivados:** CT01 e CT02.

---

### Thiago Figueiredo

**Funcionalidade:** Fazer pedido

**Riscos relacionados:**

* **R02:** O sistema pode impedir a finalização de um pedido quando existe pelo menos um produto no carrinho.
* **R03:** O sistema pode permitir a tentativa de finalização de um pedido com o carrinho vazio.

**Técnica escolhida:** Particionamento de Equivalência

**Por que a técnica foi escolhida?**

A técnica foi escolhida porque permite dividir as situações do carrinho em classes válidas e inválidas, considerando se existe ou não pelo menos um produto antes da tentativa de finalização do pedido.

**Aplicação da técnica:**

* **Classe válida:** carrinho possui pelo menos um produto.
* **Classe inválida:** carrinho não possui nenhum produto.

**Casos derivados:** CT03 e CT04.

---

### Henrique Mello

**Funcionalidade:** Criar conta

**Risco relacionado:** R04

**Técnica escolhida:** Tabela de Decisão

**Por que a técnica foi escolhida?**

A técnica foi escolhida porque permite analisar diferentes combinações de condições relacionadas aos dados utilizados no cadastro e verificar se o sistema apresenta o comportamento esperado para cada combinação.

**Condições consideradas:**

* Dados de cadastro válidos;
* E-mail já cadastrado ou não cadastrado.

**Casos derivados:** CT05 e CT06.

---

# 3. Projeto dos Casos de Teste

## 3.1 Casos de teste

### CT01: Pesquisar restaurantes por uma especialidade existente

**Integrante responsável:** Gabriel Tadeu Matiolla
**Funcionalidade:** Pesquisar restaurantes por especialidade
**Risco relacionado:** R01
**Técnica utilizada:** Particionamento de Equivalência

**Pré-condição:** A aplicação está disponível e o usuário consegue acessar a funcionalidade de pesquisa por especialidade.

**Dados de entrada:** Especialidade "Italiana".

**Passos:**

1. Acessar a aplicação LocalEats.
2. Acessar a funcionalidade de pesquisa por especialidade.
3. Informar ou selecionar a especialidade "Italiana".
4. Realizar a pesquisa.

**Resultado esperado:** O sistema deve apresentar os restaurantes correspondentes à especialidade pesquisada.

---

### CT02: Pesquisar uma especialidade sem restaurantes correspondentes

**Integrante responsável:** Gabriel Tadeu Matiolla
**Funcionalidade:** Pesquisar restaurantes por especialidade
**Risco relacionado:** R01
**Técnica utilizada:** Particionamento de Equivalência

**Pré-condição:** A aplicação está disponível e o usuário consegue acessar a funcionalidade de pesquisa por especialidade.

**Dados de entrada:** Especialidade "Comida de Marte".

**Passos:**

1. Acessar a aplicação LocalEats.
2. Acessar a funcionalidade de pesquisa por especialidade.
3. Informar ou selecionar "Comida de Marte".
4. Realizar a pesquisa.

**Resultado esperado:** O sistema deve informar que não existem restaurantes correspondentes à pesquisa, sem apresentar restaurantes de outras especialidades como resultado.

---

### CT03: Finalizar pedido com produto no carrinho

**Integrante responsável:** Thiago Figueiredo
**Funcionalidade:** Fazer pedido
**Risco relacionado:** R02
**Técnica utilizada:** Particionamento de Equivalência

**Pré-condição:** O usuário está na aplicação e existe um restaurante com pelo menos um produto disponível.

**Dados de entrada:** Um produto disponível no restaurante.

**Passos:**

1. Acessar um restaurante.
2. Selecionar um produto.
3. Adicionar o produto ao carrinho.
4. Acessar o carrinho.
5. Tentar finalizar o pedido.

**Resultado esperado:** O produto deve ser adicionado ao carrinho, o total deve ser atualizado e o sistema deve permitir a finalização do pedido.

---

### CT04: Tentar finalizar pedido com carrinho vazio

**Integrante responsável:** Thiago Figueiredo
**Funcionalidade:** Fazer pedido
**Risco relacionado:** R03
**Técnica utilizada:** Particionamento de Equivalência

**Pré-condição:** O carrinho não possui nenhum produto.

**Dados de entrada:** Nenhum produto.

**Passos:**

1. Acessar o carrinho sem adicionar produtos.
2. Verificar as opções disponíveis para finalização do pedido.
3. Tentar realizar a finalização do pedido, caso a opção esteja disponível.

**Resultado esperado:** O sistema não deve permitir a finalização de um pedido quando o carrinho estiver vazio.

---

### CT05: Criar conta com dados válidos

**Integrante responsável:** Henrique Mello
**Funcionalidade:** Criar conta
**Risco relacionado:** R04
**Técnica utilizada:** Tabela de Decisão

**Pré-condição:** O usuário não possui uma conta cadastrada com o e-mail utilizado no teste.

**Dados de entrada:**

* Nome completo válido;
* E-mail ainda não cadastrado;
* Senha válida.

**Passos:**

1. Acessar a opção de criação de conta.
2. Informar o nome completo.
3. Informar um e-mail ainda não cadastrado.
4. Informar uma senha válida.
5. Confirmar o cadastro.

**Resultado esperado:** O sistema deve permitir a criação da conta utilizando os dados informados.

---

### CT06: Tentar criar conta com e-mail já cadastrado

**Integrante responsável:** Henrique Mello
**Funcionalidade:** Criar conta
**Risco relacionado:** R04
**Técnica utilizada:** Tabela de Decisão

**Pré-condição:** Já existe uma conta cadastrada utilizando o e-mail informado.

**Dados de entrada:**

* Nome completo válido;
* E-mail já cadastrado;
* Senha válida.

**Passos:**

1. Acessar a opção de criação de conta.
2. Informar o nome completo.
3. Informar um e-mail que já esteja cadastrado.
4. Informar uma senha válida.
5. Confirmar o cadastro.

**Resultado esperado:** O sistema deve impedir a criação de uma nova conta com o mesmo e-mail e apresentar uma mensagem informando que o e-mail já está cadastrado.

---

## 3.2 Matriz de rastreabilidade

| Integrante             | Funcionalidade                           | Risco ou requisito                                                                                                   | Técnica utilizada               | Casos de teste |
| :--------------------- | :--------------------------------------- | :------------------------------------------------------------------------------------------------------------------- | :------------------------------ | :------------- |
| Gabriel Tadeu Matiolla | Pesquisar restaurantes por especialidade | R01: A pesquisa pode não retornar corretamente os restaurantes ou não tratar adequadamente pesquisas sem resultados. | Particionamento de Equivalência | CT01 e CT02    |
| Thiago Figueiredo      | Fazer pedido                             | R02: O sistema pode impedir a finalização de pedido com produto no carrinho.                                         | Particionamento de Equivalência | CT03           |
| Thiago Figueiredo      | Fazer pedido                             | R03: O sistema pode permitir tentativa de finalização com carrinho vazio.                                            | Particionamento de Equivalência | CT04           |
| Henrique Mello         | Criar conta                              | R04: O sistema pode permitir cadastro com e-mail já registrado.                                                      | Tabela de Decisão               | CT05 e CT06    |

---

# Uso de Inteligência Artificial

**Ferramenta utilizada:** Gemini.

**Como foi utilizada:**

**Como as respostas foram verificadas:** As sugestões foram comparadas com os comportamentos observados na aplicação LocalEats durante as atividades anteriores e com os requisitos definidos para esta atividade. Foram mantidas apenas as sugestões compatíveis com as funcionalidades e comportamentos identificados pela equipe.
