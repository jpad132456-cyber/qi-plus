# CLAUDE.md

## Projeto

## Publico alvo

Uma pessoa só: o dono ou executivo de topo de uma empresa média. Olha para a rentabilidade, paga uma conta grande de IA e não vê a produtividade subir. Os problemas que ele enxerga são inconsistência nos documentos e dado inventado pela IA que só aparece lá na frente.

## Comandos

Deploy: o diretório está ligado ao projeto Vercel qi-plus (.vercel/, ignorado no git), com deploy automático a partir dos push no main.

Importante! -> o Push altera o site que está no ar, ele deve somente ser usado com permissão explicita e para enviar alterações em estado adequado para o publico. Sempre verifique se você tem permissão para dar o push e se o codigo está adequado para isso, se a resposta nao for clara, pergunte

## Arquitetura

Antes de qualquer mudança visual (cor, fonte, espaçamento, componente novo), leia DESIGN.md — ele é a regra; o CSS atual ainda não segue toda a escala de fontes.

backup/index-v1..v5.html são versões antigas congeladas — não editar nem usar como referência do estado atual.

- logos/ guarda os SVGs das ferramentas (LobeHub Icons, MIT), mas no script eles estão embutidos em base64 no objeto LOGOS; alterar um arquivo em logos/ não muda a página sozinho.

### Estrutura da página

Há uma seção de prova social comentada, pronta para ativar quando houver dados reais.

Peças que dependem umas das outras:

- **O fio**: qualquer mudança de altura/posição das seções pode desalinhar o fio — Depois de mexer em layout, confira o fio ao longo da página inteira.
