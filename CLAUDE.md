## BUILDLOG

Ao final de cada sessão de trabalho que altere o produto, atualize o `BUILDLOG.md` na raiz
do repositório. Se já existir uma seção com a data de hoje (`## AAAA-MM-DD`), acrescente
nela; senão, crie uma nova no topo (logo abaixo do cabeçalho). Use os campos:

**Feito:** o que mudou, em linguagem de produto (não de código).
**Por quê:** a motivação — pedido de usuário, bug, aposta, aprendizado.
**Decisões:** escolhas relevantes e o motivo.
**Travou/aprendi:** o que deu errado, mudou de rumo ou surpreendeu.
**Próximo:** o passo seguinte.

1–3 linhas por campo; omita campos sem conteúdo. Não registre sessões que só mexem em
formatação, dependências ou refactors sem efeito visível.

Nunca escreva no BUILDLOG: segredos, tokens, nomes de variáveis de ambiente, IPs,
hostnames, domínios internos, detalhes de infraestrutura, valores financeiros, dados de
usuários, nomes de clientes ou vulnerabilidades de segurança.

Faça commit do BUILDLOG junto com o trabalho da sessão e dê push. O BIP Reporter lê o arquivo
pelo GitHub, na branch padrão.
