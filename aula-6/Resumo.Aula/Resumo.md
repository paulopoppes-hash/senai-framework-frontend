# Aula 06 â€” Projetos Front-End

**Disciplina:** Frameworks Front-end  
**Foco:** planejamento, requisitos e acompanhamento de projetos Front-End.

---

## VisÃ£o geral

Projetos Front-End envolvem pessoas, tecnologias, prazos e integraÃ§Ãµes. Sem um processo de gestÃ£o, requisitos podem ficar confusos, tarefas podem ser esquecidas e conflitos no Git ou retrabalho se tornam mais provÃ¡veis. A gestÃ£o organiza esse caminho para que a equipe faÃ§a entregas incrementais e acompanhe o progresso.

```text
Ideia â†’ requisitos â†’ backlog â†’ prioridades e estimativas â†’ desenvolvimento â†’ revisÃ£o e testes â†’ entrega
```

## Requisitos, histÃ³rias e tarefas

O escopo pode ser detalhado em nÃ­veis diferentes:

| NÃ­vel | Papel | Exemplo |
| --- | --- | --- |
| Requisito | Necessidade do sistema | Permitir o gerenciamento de tarefas. |
| User story | Necessidade descrita pela pessoa usuÃ¡ria | Como usuÃ¡rio, quero criar uma tarefa. |
| Tarefa tÃ©cnica | AÃ§Ã£o necessÃ¡ria para implementar a histÃ³ria | Criar formulÃ¡rio, validar campos, integrar API e testar. |

Esse desdobramento torna o trabalho compreensÃ­vel, distribuÃ­vel e verificÃ¡vel.

## Backlog, priorizaÃ§Ã£o e estimativas

O **product backlog** reÃºne funcionalidades, melhorias, correÃ§Ãµes e dÃ©bitos tÃ©cnicos. Ele Ã© dinÃ¢mico: os itens sÃ£o revisados e ordenados conforme valor para o produto, dependÃªncias, riscos e prazos.

As estimativas nÃ£o sÃ£o promessas exatas; elas ajudam a comparar esforÃ§o e complexidade para planejar uma Sprint. TÃ©cnicas como *story points*, *Planning Poker* e tamanhos P/M/G podem apoiar essa conversa.

## Definition of Done e trabalho Ã¡gil

A **Definition of Done (DoD)** define quando uma tarefa estÃ¡ realmente concluÃ­da. Em um projeto Front-End, os critÃ©rios podem incluir:

- funcionalidade implementada e revisada;
- testes realizados;
- responsividade verificada;
- integraÃ§Ã£o validada, quando aplicÃ¡vel;
- documentaÃ§Ã£o atualizada e Pull Request aprovada.

O Scrum organiza entregas em Sprints, com inspeÃ§Ã£o e adaptaÃ§Ã£o frequentes. JÃ¡ o Kanban torna o fluxo visÃ­vel, por exemplo:

```text
Backlog â†’ Para fazer â†’ Em andamento â†’ RevisÃ£o â†’ ConcluÃ­do
```

O uso de branches tambÃ©m contribui para o fluxo: `main` mantÃ©m a versÃ£o estÃ¡vel, `develop` integra o trabalho e `feature/<nome>` isola uma funcionalidade.

## Atividade prÃ¡tica â€” GestÃ£o do PII

Na atividade, foi elaborado um plano de gestÃ£o para o Projeto Integrador Interdisciplinar. O repositÃ³rio documenta um backlog com prioridades e estimativas, um quadro Kanban, quatro Sprints, estratÃ©gia de branches e critÃ©rios de DoD. Assim, os conceitos da aula foram aplicados Ã  organizaÃ§Ã£o do desenvolvimento de front-end, back-end, integraÃ§Ã£o, testes e documentaÃ§Ã£o.

**RepositÃ³rio da atividade:** [Senai-Gestao-PII](https://github.com/paulopoppes-hash/Senai-Gestao-PII)

## SÃ­ntese

Gerenciar um projeto Front-End Ã© transformar uma ideia em entregas menores, priorizadas e verificÃ¡veis. Requisitos claros, backlog, estimativas, Kanban ou Scrum, branches e uma DoD compartilhada reduzem incertezas e ajudam a equipe a entregar com qualidade.

