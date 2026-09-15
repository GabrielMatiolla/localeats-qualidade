# Atividade 1: Fundamentos e Características da Qualidade no LocalEats

## Tarefa 1: Fundamentos da qualidade

### Necessidades

| Tipo | Necessidade | Interessado | Consequência se não for atendida |
| :--- | :--- | :--- | :--- |
| Explícita | Permitir que o usuário filtre restaurantes por especialidade (ex: Italiana, Japonesa). | Usuários (clientes) | O usuário terá dificuldade em achar o que deseja comer, o que pode fazê-lo desistir de usar a aplicação. |
| Explícita | Permitir que o usuário consiga fazer um pedido no restaurante escolhido. | Usuários e Restaurantes | A aplicação perde o seu propósito principal, impedindo os restaurantes de venderem e os usuários de comprarem. |
| Implícita | O sistema deve responder rapidamente às interações, carregando a lista de restaurantes sem lentidão. | Usuários | Se o site demorar muito para carregar, o usuário ficará frustrado e abandonará a página, achando que o sistema travou. |
| Implícita | O sistema deve garantir a segurança e a privacidade dos dados pessoais dos usuários. | Usuários e Negócio (LocalEats) | Vazamento de dados pode gerar perda total de confiança na plataforma, processos legais e abandono em massa do aplicativo. |

### Justificativa 
**Um sistema que implementa todas as funcionalidades explicitamente solicitadas pode, ainda assim, apresentar baixa qualidade?**
Sim. Mesmo que o LocalEats permita fazer pedidos e filtrar restaurantes, se ele não garantir a segurança dos dados dos usuários (necessidade implícita), ele terá baixíssima qualidade. O usuário não fará pedidos se não confiar na plataforma, tornando as funcionalidades explícitas inúteis na prática.

---

## Tarefa 2: Exploração da aplicação

| Integrante | Funcionalidade | O que foi realizado | O que foi observado | Evidência |
| :--- | :--- | :--- | :--- | :--- |
| Gabriel Tadeu Matiolla | Pesquisar restaurantes por especialidade | Realizei uma busca com o termo "Italiana" (esperado) e outra busca pesquisando por "Comida de Marte (inválido). | Na busca Válida ele me retornou 3 restaurantes Italianos, na busca inválida ele me retornou nenhum restaurante com a mensagem "Nenhum restaurante encontrado."| Gabriel - pesquisa Italiana.png |
| Thiago Figueiredo | Realizar Pedidos | Realizei um pedido adicionando um produto ao carrinho e finalizei o pedido (esperado). Também tentei finalizar um pedido sem adicionar nenhum item (inválido). | No uso válido, o produto foi adicionado ao pedido, o total foi atualizado e o pedido pôde ser finalizado. No uso inválido, a opção de finalizar o pedido não aparece, pois nenhum item foi adicionado. | [nome-arquivo-evidencia.png] |
| Henrique Mello | Criar a conta na plataforma LocalEats | Criei a conta na plataforma com nome completo, email e senha (esperado). Realizei um teste para saber se é possivel criar uma conta com o mesmo email já cadastrado (inválida)| Na busca válida ele criou sem problemas a conta, já na invalida ele deu uma mensagem de email já cadastrado, o que achei bom, pois é uma questão de segurança.| Henrique-teste-login.png |

---

## Tarefa 3: Requisitos e características de qualidade

| Integrante | Requisito de Qualidade | Característica ou subcaracterística | Justificativa | Como avaliar |
| :--- | :--- | :--- | :--- | :--- |
| Gabriel Tadeu Matiolla | O sistema deve exibir uma mensagem clara e amigável caso a pesquisa não retorne nenhum restaurante. | Usabilidade, Prevenção contra erros | No LocalEats, se o usuário buscar por um restaurante não cadastrado, ele precisa entender facilmente que a busca não teve resultados, evitando frustração ou a sensação de que o site travou. | Realizar buscas com termos inexistentes e observar se a interface exibe a mensagem de feedback adequado na tela. |
| Thiago Figueiredo | O sistema deve permitir que o usuário realize um pedido de forma rápida e com poucos passos, apresentando as informações do pedido de maneira clara antes da finalização. | Eficiência | No LocalEats, o usuário precisa conseguir adicionar um produto, verificar o pedido e finalizá-lo sem precisar realizar etapas desnecessárias. Isso torna o processo de realização do pedido mais rápido e prático. | Realizar um pedido desde a escolha de um produto até a finalização e observar a quantidade de etapas necessárias, verificando se o pedido pode ser concluído de forma simples e sem etapas desnecessárias. |
| Henrique Mello | O sistema deve exibir uma mensagem ou alerta que já existe uma conta com o email cadastrado | Segurança | Se o usuário já criou a conta no LocalEats então deve aparecer uma mensagem de que já existe uma conta com aquele mesmo email. | Realizar o teste de criar uma conta com o mesmo email já registrado anteriormente e ver se aparece a mensagem de "Email já cadastrado". |

---

## Uso de inteligência artificial

**Ferramenta utilizada:**


**Como foi utilizada:**


**Como as respostas foram verificadas:**
