# BUILDLOG

Diário de construção deste projeto. Uma seção por dia, mais recente no topo.
O BIP Reporter lê as seções pela data do cabeçalho — mantenha o formato `## AAAA-MM-DD`.

## 2026-09-23

**Feito:** Transição do ecossistema de agentes para papéis especializados (Backend Builder, Frontend Builder, Infra Engineer, UI/UX Designer e Investigator), com remoção do Builder genérico e do Maestro Design; Maestro atualizado com execução paralela por padrão e fluxo formal de diagnóstico de bugs; partitura Orchestrator Default atualizada para a nova estrutura.
**Por quê:** O Builder genérico causava sobreposição de escopo e gargalos de contexto; a especialização divide o trabalho com clareza entre arquitetura, implementação e investigação.
**Decisões:** Priorizar execução concorrente de tarefas independentes na orquestração e criar o papel de Investigator dedicado a diagnóstico antes de qualquer correção.
**Travou/aprendi:** Papéis generalistas tendem a acumular responsabilidades concorrentes; manter tarefas atômicas e atribuídas por domínio acelera a orquestração autônoma.
**Próximo:** Consolidar os fluxos de trabalho nos projetos ativos usando os novos papéis especializados.
