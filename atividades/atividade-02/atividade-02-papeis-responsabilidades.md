# Atividade 2: Organização da Qualidade no LocalEats

## Identificação

**Turma:** Qualidade de Software - Terça/Noite - POA

**Equipe:** - 

**Data:** 18/09/2026

**Elemento de Competência:** Identificar papéis, responsabilidades e competências relacionadas às atividades de qualidade e testes.

---

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Gabriel Tadeu Matiolla | @GabrielMatiolla|
| Thiago Figueiredo | @ThiagoF1703|
| Henrique Mello | @eiHenriqueMello|

## Tarefa 1: Diagnóstico da situação

| Problema identificado | Possível consequência para o produto ou para a equipe |
| :--- | :--- |
| Critérios de funcionalidade pronta não estão claros | O Desenvolvedor acha que terminou, mas o PO ou QA reprovam porque faltou algo, gerando retrabalho e frustração. |
| Defeitos são identificados, mas nem sempre registrados ou acompanhados. | Erros conhecidos são esquecidos e acabam chegando aos usuários em produção, piorando a reputação do LocalEats. |
| Não está claro quem pode aprovar a disponibilização de uma nova versão. | O código pode subir para produção com falhas críticas porque alguém subiu sem permissão, ou o lançamento atrasa porque ninguém quer assumir a responsabilidade. |

### Justificativa (até cinco linhas)
**A qualidade do LocalEats deve ser responsabilidade exclusiva do profissional de QA? Justifiquem.**
Não. A qualidade é uma responsabilidade compartilhada por toda a equipe. Se apenas o QA testa no final do ciclo, ele se torna um grande problema e os bugs ficam mais caros para corrigir. O Analista deve garantir bons requisitos e o Desenvolvedor deve aplicar testes unitários e boas práticas de código, deixando o QA atuar de forma mais estratégica e preventiva.

---

## Tarefa 2: Papéis e competências

| Integrante | Papel analisado | Responsabilidades relacionadas à qualidade | Competências técnicas | Competências comportamentais |
| :--- | :--- | :--- | :--- | :--- |
| Gabriel Tadeu Matiolla | Desenvolvedor | Desenvolver funcionalidades aplicando boas práticas, criar e executar testes unitários e de integração, realizar revisões de código (code review) dos colegas e corrigir defeitos identificados. | Domínio da linguagem de programação e arquitetura, conhecimento em frameworks de automação/testes unitários e versionamento de código (Git). | Colaboração e trabalho em equipe, pensamento crítico para antecipar possíveis falhas lógicas, responsabilidade e comunicação clara para relatar bloqueios técnicos. |
| Thiago Figuereido | [Papel 2, ex: QA] | [Responsabilidades] | [Competências técnicas] | [Competências comportamentais] |
| Henrique Mello | [Papel 3, ex: Analista de Negócio / PO] | [Responsabilidades] | [Competências técnicas] | [Competências comportamentais] |

---

## Tarefa 3: Matriz de responsabilidades (RACI)

| Atividade de qualidade | Desenvolvedor | QA / Analista de Teste | Analista de Negócio / PO |
| :--- | :--- | :--- | :--- |
| Definir critérios de aceitação | C | C | R, A |
| Revisar requisitos | R | R | A |
| Implementar a funcionalidade | R, A | I | I |
| Revisar o código | R, A | I | I |
| Criar testes unitários | R, A | C | I |
| Planejar e executar testes do sistema | I | R, A | C |
| Registrar e acompanhar defeitos | R | R | I |
| Priorizar a correção dos defeitos | I | C | R, A |
| Aprovar a disponibilização da versão | C | C | R, A |

### Lacuna ou conflito encontrado
Observando a matriz, a atividade de "Revisar o código" concentra as responsabilidades (R e A) exclusivamente no Desenvolvedor. Se não houver uma cultura de revisão por pares (onde um desenvolvedor revisa o código do outro), o código pode seguir para as próximas etapas sem uma dupla verificação técnica, criando um ponto cego no processo.

---


### Práticas recomendadas

| Prática recomendada | Problema que ajuda a resolver | Papéis envolvidos |
| :--- | :--- | :--- |
| Reunião de "Three Amigos" (Três Amigos) | Falta de clareza nos critérios de quando a funcionalidade está realmente pronta. | Desenvolvedor, QA e Analista de Negócio/PO. |
| Desk Check (Validação Conjunta) | Funcionalidades chegando à etapa de testes formais ou aos usuários com defeitos muito básicos. | Desenvolvedor e QA. |

---

## Uso de inteligência artificial

**Ferramenta utilizada:**
Gemini.

**Como foi utilizada:**
Usada para estrutura o Markdown e verificação da matriz RACI.

**Como as respostas foram verificadas:**
