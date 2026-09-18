# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## 1. Identificação

**Turma:** Qualidade de Software - Terça/Noite - POA

**Equipe:** - 

**Data:** 18/09/2026

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Gabriel Tadeu Matiolla | @GabrielMatiolla|
| Thiago Figueiredo | @ThiagoF1703|
| Henrique Mello | @eiHenriqueMello|

**Elemento de Competência:** Planejar e projetar testes selecionando técnicas adequadas.

**Aplicação:** <https://local-eats-unisenac.vercel.app/>

---

## Tarefa 1: Planejamento dos testes

### 1.1 Objetivo dos testes
Verificar se as regras de negócio críticas do LocalEats (como limite de valores para pedidos, bloqueios de segurança no login e precisão de filtros) funcionam corretamente, garantindo que o sistema impeça ações inválidas e proporcione uma experiência segura ao usuário.

### 1.2 Escopo

| Integrante | Funcionalidade incluída | O que será verificado |
| :--- | :--- | :--- |
| Gabriel Tadeu Matiolla | Fazer pedido | Regra de valor mínimo de R$ 20,00 para permitir a finalização de um pedido com entrega. |
| Thiago Figueiredo | Entrar no sistema | [Ex: Regra de bloqueio de conta após múltiplas tentativas inválidas de login.] |
| Henrique Mello | Filtrar restaurantes por especialidade | Exibição exclusiva dos restaurantes correspondentes à categoria selecionada e comportamento do sistema diante de filtros sem resultados. |

| Funcionalidade não incluída | Justificativa |
| :--- | :--- |
| Consultar pedidos | O foco atual da sprint de testes é a jornada de conversão e entrada (autenticação, busca e checkout). A consulta pós-venda será testada no próximo ciclo. |

### 1.3 Abordagem

| Item | Decisão da equipe | Justificativa |
| :--- | :--- | :--- |
| Níveis de teste | Sistema | O fluxo será analisado de ponta a ponta pela interface do usuário, validando a integração das regras. |
| Tipos de teste | Funcional | O objetivo é validar o comportamento das regras de negócio (o "que" o sistema faz). |
| Perspectiva | Caixa-preta | Os testes serão baseados nos requisitos e na interface (inputs e outputs), sem acesso ao código-fonte. |
| Técnicas de teste | Análise de valor limite, Transição de estados e Particionamento de equivalência. | As regras escolhidas envolvem fronteiras numéricas (valores mínimos), contadores de estado (bloqueios) e categorias lógicas (filtros). |

### 1.4 Ambiente e responsabilidades

| Item | Definição |
| :--- | :--- |
| Ambiente necessário | Navegador Google Chrome atualizado; acesso à URL `https://local-eats-unisenac.vercel.app/`; contas de teste de usuário criadas; restaurantes cadastrados. |
| Responsáveis pelo planejamento | A equipe completa (Gabriel, Thiago e Henrique). |
| Responsáveis pela especificação dos casos | Cada integrante especifica os casos da funcionalidade que escolheu. |
| Responsáveis pela futura execução | Analistas de QA ou Desenvolvedores em esquema de teste cruzado (Peer Testing). |

### 1.5 Critérios

| Critério | Definição da equipe |
| :--- | :--- |
| Entrada | Ambiente de homologação no ar, funcionalidades desenvolvidas e especificações de regras de negócio aprovadas. |
| Saída | 100% dos casos de teste prioritários executados, sem defeitos críticos (prioridade Alta) bloqueando o fluxo principal. |
| Suspensão | Indisponibilidade do servidor do LocalEats ou falha crítica no banco de dados que impeça a criação e manipulação de usuários e pedidos. |

---

## Tarefa 2: Riscos e técnicas de teste

### 2.1 Análise dos riscos

| ID | Integrante | Funcionalidade | Risco | Consequência | Probabilidade | Impacto | Prioridade | Justificativa |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| R01 | Gabriel Tadeu Matiolla | Fazer pedido | O sistema permitir a finalização de pedidos com entrega abaixo de R$ 20,00. | Prejuízo financeiro para os restaurantes devido aos custos logísticos de entregas de baixo valor. | Média | Alto | Alta | Afeta diretamente a margem de lucro e as regras contratuais com os parceiros. |
| R02 | Thiago Figueiredo | Entrar no sistema | [Ex: Um script malicioso conseguir testar senhas infinitamente sem bloqueio.] | [Vazamento e roubo de contas de usuários.] | [Baixa/Média] | [Alto] | [Alta] | [Risco grave de segurança e exposição de dados de clientes.] |
| R03 | Henrique Mello | Filtrar restaurantes | Exibir restaurantes de especialidades incorretas ou falhar em limpar o filtro aplicado. | Frustração do usuário na navegação, perda de vendas por falta de visibilidade do catálogo e quebra de usabilidade. | Média | Médio | Média | Prejudica diretamente a experiência de descoberta e escolha de restaurantes pelo cliente. |

### 2.2 Aplicação da técnica

**Integrante responsável:** Gabriel Tadeu Matiolla

**Funcionalidade:** Fazer pedido

**Risco relacionado:** R01

**Técnica escolhida:** Análise de Valor Limite

*Por que a técnica foi escolhida?*
O requisito estabelece uma fronteira numérica exata (R$ 20,00). Erros de lógica de programação (usar `>` em vez de `>=`) costumam ocorrer exatamente nas bordas das restrições lógicas.

*Aplicação da técnica:*
- Limite inferior inválido: R$ 19,99 (Espera-se bloqueio).
- Limite válido exato: R$ 20,00 (Espera-se aprovação).

*Casos derivados:* CT01 e CT02.

**Integrante responsável:** Thiago Figueiredo
**Funcionalidade:** [Entrar no sistema]
**Risco relacionado:** [R02]
**Técnica escolhida:** [Transição de Estados ou Valores-Limite]
*Por que a técnica foi escolhida?*
[Explicar o motivo]
*Aplicação da técnica:*
[Apresentar transições de logado/bloqueado ou contagem de tentativas 4, 5, 6]
*Casos derivados:* [CT03 e CT04]

**Integrante responsável:** Henrique Mello

**Funcionalidade:** Filtrar restaurantes por especialidade

**Risco relacionado:** R03

**Técnica escolhida:** Particionamento de Equivalência

*Por que a técnica foi escolhida?*
A funcionalidade de filtragem trabalha com agrupamentos discretos de dados (categorias de especialidades cadastradas vs. inexistentes). Aplicar a partição em classes de equivalência permite validar todas as opções da interface reduzindo a redundância e garantindo cobertura tanto para pesquisas com retorno válido quanto para pesquisas sem resultados.

*Aplicação da técnica:*
- **Classe Válida 1:** Especialidade existente com estabelecimentos associados (Ex: "Japonesa").
- **Classe Válida 2:** Troca de filtro ativo ou remoção do filtro ("Todas as especialidades").
- **Classe Inválida:** Seleção/combinação de especialidade sem nenhum estabelecimento cadastrado no momento (Ex: "Mexicana").

*Casos derivados:* CT05 e CT06.

---

## Tarefa 3: Casos de teste e rastreabilidade

### 3.1 Especificação dos casos de teste

**CT01: Impedir finalização de pedido abaixo do valor mínimo (R$ 19,99)**
**Integrante responsável:** Gabriel Tadeu Matiolla
**Funcionalidade:** Fazer pedido
**Risco relacionado:** R01
**Técnica utilizada:** Análise de valor limite
**Pré-condição:** Usuário autenticado, restaurante aberto, endereço cadastrado no raio de entrega e taxa de frete desconsiderada para a soma mínima.
**Dados de entrada:** Itens no carrinho somando o subtotal exato de R$ 19,99.
**Passos:**
1. Acessar o restaurante selecionado.
2. Adicionar itens ao carrinho até que o subtotal atinja R$ 19,99.
3. Clicar no carrinho para ir à tela de checkout.
4. Tentar clicar no botão de "Finalizar pedido".
**Resultado esperado:** O botão de finalização deve estar desabilitado ou o sistema deve exibir uma mensagem informando que o valor mínimo para entrega é de R$ 20,00, mantendo o pedido em aberto.

**CT02: Permitir finalização de pedido no valor limite exato (R$ 20,00)**
**Integrante responsável:** Gabriel Tadeu Matiolla
**Funcionalidade:** Fazer pedido
**Risco relacionado:** R01
**Técnica utilizada:** Análise de valor limite
**Pré-condição:** Usuário autenticado, restaurante aberto.
**Dados de entrada:** Itens no carrinho somando o subtotal exato de R$ 20,00. Forma de pagamento válida informada.
**Passos:**
1. Acessar o restaurante selecionado.
2. Adicionar itens ao carrinho até que o subtotal atinja exatamente R$ 20,00.
3. Acessar o checkout e confirmar o endereço de entrega e pagamento.
4. Clicar no botão de "Finalizar pedido".
**Resultado esperado:** O sistema deve processar o pagamento e direcionar o usuário para a tela de confirmação, alterando o status do pedido para "Criado".

**CT03: [Título do caso do Colega 2]**
**Integrante responsável:** Thiago Figueiredo
**Funcionalidade:** [Nome]
**Risco relacionado:** [ID]
**Técnica utilizada:** [Nome]
**Pré-condição:** [Condição]
**Dados de entrada:** [Dados]
**Passos:**
1. [Passo 1]
2. [Passo 2]
**Resultado esperado:** [Resultado]

**CT04: [Título do segundo caso Thiago Figueiredo]**
*(Replicar a estrutura acima)*

**CT05: Filtrar estabelecimentos por categoria existente válida ("Japonesa")**
**Integrante responsável:** Henrique Mello
**Funcionalidade:** Filtrar restaurantes por especialidade
**Risco relacionado:** R03
**Técnica utilizada:** Particionamento de equivalência
**Pré-condição:** Aplicação aberta na tela inicial ("Explorar") e restaurantes de diferentes categorias previamente cadastrados no sistema.
**Dados de entrada:** Clique na opção/tag de especialidade "Japonesa".
**Passos:**
1. Acessar a página principal de exploração do LocalEats.
2. Localizar o menu de categorias de especialidades.
3. Clicar na categoria "Japonesa".
4. Verificar a lista de restaurantes retornada na tela.
**Resultado esperado:** A tela deve atualizar e listar exclusivamente os restaurantes cadastrados sob a especialidade "Japonesa", ocultando as outras categorias.

**CT06: Exibir mensagem adequada ao filtrar especialidade sem restaurantes cadastrados**
**Integrante responsável:** Henrique Mello
**Funcionalidade:** Filtrar restaurantes por especialidade
**Risco relacionado:** R03
**Técnica utilizada:** Particionamento de equivalência
**Pré-condição:** Usuário na tela de busca/exploração e pelo menos uma categoria sem restaurantes vinculados no banco de dados (ex.: "Mexicana").
**Dados de entrada:** Clique na categoria "Mexicana".
**Passos:**
1. Acessar a página inicial de restaurantes.
2. Selecionar a especialidade "Mexicana".
3. Observar a listagem exibida e o estado visual da tela.
**Resultado esperado:** O sistema não deve apresentar erro de tela em branco ou congelamento. Deve exibir um feedback claro ao usuário (ex.: *"Nenhum restaurante encontrado para esta especialidade"*) acompanhado da opção de limpar ou alterar o filtro.

### 3.2 Matriz de rastreabilidade

| Integrante | Funcionalidade | Risco ou requisito | Técnica utilizada | Casos de teste |
| :--- | :--- | :--- | :--- | :--- |
| Gabriel Tadeu Matiolla | Fazer pedido | R01: Finalizar pedido abaixo do valor mínimo | Análise de valor limite | CT01 e CT02 |
| Thiago Figueiredo | Entrar no sistema | [R02: Bloqueio de conta por segurança] | [Técnica usada] | [CT03 e CT04] |
| Henrique Mello | Filtrar restaurantes | R03: Filtro trazer dados incorretos ou indisponíveis | Particionamento de equivalência | CT05 e CT06 |

---

## Uso de inteligência artificial

**Ferramenta utilizada:**
Gemini

**Como foi utilizada:**
A ferramenta foi consultada pontualmente para revisar a escrita dos casos de teste e garantir o alinhamento teórico na especificação das classes de equivalência (válidas e inválidas).

**Uma sugestão que precisou ser alterada ou rejeitada:**
A IA sugeriu criar um caso de teste injetando scripts de busca via URL. A sugestão foi descartada por fugir do escopo de testes funcionais de caixa-preta baseados na interface do usuário.

**Como as respostas foram verificadas:**
Validou-se visualmente a funcionalidade de filtros no ambiente do LocalEats (`https://local-eats-unisenac.vercel.app/`) para confirmar o comportamento real da aplicação em cada cenário.