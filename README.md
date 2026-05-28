 Sistema de Prevenção de Evasão Acadêmica

 Disciplina

Processos de Software e Engenharia de Requisitos

 Objetivo do Projeto

Este projeto tem como objetivo desenvolver um Sistema de Prevenção de Evasão Acadêmica, permitindo identificar alunos com risco de evasão através do acompanhamento de frequência, desempenho acadêmico e emissão de alertas automáticos.

---

 Product Backlog

| Prioridade | Requisito Funcional | Descrição                                                     |
| ---------- | ------------------- | ------------------------------------------------------------- |
| 1          | RF01                | O sistema deve identificar alunos com risco de evasão.        |
| 2          | RF02                | O sistema deve emitir alertas automáticos para coordenadores. |
| 3          | RF03                | O sistema deve permitir acompanhamento de frequência.         |
| 4          | RF04                | O sistema deve gerar relatórios de desempenho acadêmico.      |
| 5          | RF05                | O sistema deve enviar notificações aos alunos.                |
| 6          | RF06                | O sistema deve permitir cadastro de alunos.                   |
| 7          | RF07                | O sistema deve permitir cadastro de disciplinas.              |
| 8          | RF08                | O sistema deve registrar notas dos alunos.                    |
| 9          | RF09                | O sistema deve permitir autenticação de usuários.             |
| 10         | RF10                | O sistema deve armazenar histórico acadêmico.                 |

---

 User Stories

 User Story 1 – Identificação de Risco de Evasão

 CARD

Como coordenador de curso,
eu quero visualizar alunos com risco de evasão,
para que eu possa agir antes que o aluno abandone o curso.

 CONVERSATION

* O sistema deve analisar notas e frequência.
* Alunos com frequência abaixo de 75% devem ser sinalizados.
* O sistema deve atualizar os dados automaticamente.

 CONFIRMATION

* [ ] O sistema deve destacar alunos em risco.
* [ ] O coordenador deve conseguir visualizar a lista completa.
* [ ] O sistema deve atualizar os dados diariamente.

---

 User Story 2 – Alertas Automáticos

 CARD

Como coordenador,
eu quero receber alertas automáticos,
para acompanhar alunos com baixo desempenho.

### CONVERSATION

* Alertas devem aparecer no painel principal.
* O sistema deve considerar faltas e notas baixas.
* O alerta deve desaparecer quando o aluno melhorar.

 CONFIRMATION

* [ ] O sistema deve emitir alerta visual.
* [ ] O sistema deve atualizar automaticamente os alertas.
* [ ] O coordenador deve conseguir filtrar por turma.

---

 User Story 3 – Controle de Frequência

# CARD

Como professor,
eu quero registrar presença e faltas dos alunos,
para manter o acompanhamento da frequência atualizado.

 CONVERSATION

* O professor só pode registrar frequência da sua disciplina.
* O sistema deve calcular porcentagem automaticamente.
* O aluno não pode ultrapassar o limite de faltas sem alerta.

### CONFIRMATION

* [ ] O sistema deve salvar as faltas registradas.
* [ ] O sistema deve calcular a porcentagem automaticamente.
* [ ] O sistema deve exibir aviso quando o limite for atingido.

---

 User Story 4 – Relatórios Acadêmicos

 CARD

Como coordenador,
eu quero gerar relatórios acadêmicos,
para analisar o desempenho dos alunos.

 CONVERSATION

* Relatórios devem possuir notas e frequência.
* O sistema deve permitir exportação em PDF.
* O relatório deve ser organizado por semestre.

### CONFIRMATION

* [ ] O sistema deve gerar relatório completo.
* [ ] O sistema deve permitir download em PDF.
* [ ] O relatório deve apresentar médias e frequência.

---

 User Story 5 – Notificações aos Alunos

 CARD

Como aluno,
eu quero receber notificações sobre minha situação acadêmica,
para acompanhar meu desempenho no curso.

 CONVERSATION

* As notificações podem ser enviadas por e-mail.
* O sistema deve avisar sobre risco de reprovação.
* As mensagens devem ser claras e objetivas.

### CONFIRMATION

* [ ] O sistema deve enviar notificações automáticas.
* [ ] O aluno deve receber aviso de risco acadêmico.
* [ ] O sistema deve registrar o envio das mensagens.

---

 Cenários BDD

 User Story 1 – Identificação de Risco

 Cenário 01 – Caminho Feliz

```gherkin
Cenário: Sistema identifica aluno com risco de evasão

Dado que o aluno "Carlos" possui frequência de 70%
E média geral abaixo de 6,0
Quando o sistema atualizar os dados acadêmicos
Então o aluno deve ser marcado como "Em risco"
E o coordenador deve visualizar o alerta no painel
```

 Cenário 02 – Fluxo de Exceção

```gherkin
Cenário: Aluno fora do risco acadêmico

Dado que o aluno "Lucas" possui frequência acima de 80%
E média maior que 7,0
Quando o sistema verificar os dados acadêmicos
Então o aluno não deve aparecer na lista de risco
```

---

 User Story 2 – Alertas Automáticos

 Cenário 01 – Caminho Feliz

```gherkin
Cenário: Emissão de alerta automático

Dado que a aluna "Fernanda" possui muitas faltas
Quando o sistema atualizar as informações
Então um alerta deve aparecer no painel do coordenador
```

 Cenário 02 – Fluxo de Exceção

```gherkin
Cenário: Alerta removido após melhora do aluno

Dado que a aluna "Fernanda" melhorou sua frequência
Quando o sistema recalcular os dados
Então o alerta deve desaparecer do painel
```

---

 User Story 3 – Controle de Frequência

 Cenário 01 – Caminho Feliz

```gherkin
Cenário: Registro de falta realizado com sucesso

Dado que o professor está autenticado no sistema
Quando ele registrar uma falta para o aluno "João"
Então o sistema deve salvar a falta corretamente
E atualizar a porcentagem de frequência
```

 Cenário 02 – Fluxo de Exceção

```gherkin
Cenário: Tentativa de registro inválido

Dado que o professor não possui acesso à disciplina
Quando tentar registrar uma falta
Então o sistema deve bloquear a operação
E exibir mensagem de erro
```

---

 Autoavaliação INVEST

| Critério    | US1 | US2 | US3 | US4 | US5 |
| ----------- | --- | --- | --- | --- | --- |
| Independent | Sim | Sim | Sim | Sim | Sim |
| Negotiable  | Sim | Sim | Sim | Sim | Sim |
| Valuable    | Sim | Sim | Sim | Sim | Sim |
| Estimable   | Sim | Sim | Sim | Sim | Sim |
| Small       | Sim | Sim | Sim | Sim | Sim |
| Testable    | Sim | Sim | Sim | Sim | Sim |

---

 Justificativa INVEST

As histórias criadas seguem o modelo INVEST, pois possuem objetivos claros, valor para os usuários e podem ser testadas através dos critérios de aceite e cenários BDD. Além disso, as funcionalidades foram separadas em pequenas partes para facilitar o desenvolvimento e entendimento da equipe.

---

# Organização do GitHub

## Estrutura do Repositório

```bash
📁 sistema-prevencao-evasao
 ┣ 📄 README.md
 ┣ 📁 docs
 ┃ ┗ 📄 trabalho.pdf
 ┗ 📁 imagens
```

---

# Conclusão

O trabalho permitiu transformar requisitos funcionais em artefatos ágeis mais organizados e próximos da realidade do desenvolvimento de software. A utilização de User Stories e cenários BDD ajudou a melhorar o entendimento das funcionalidades e do comportamento esperado do sistema.
# trabalho2
