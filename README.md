# Sessões, buscas e navegação na wikimedia

- O sumário executivo para esta atividade pode ser visualizado no [RPUBS](http://rpubs.com/aminueza/DiscoveryHiringAnalyst2016).

- O report da inferência estatística pode ser visualizado no [RPUBS](http://rpubs.com/aminueza/inferencia-estatistica-wikimedia).

- O report dos testes de hipótese pode ser visualizado no [RPUBS](http://rpubs.com/aminueza/teste-de-hipotese-wikimedia).

Este repo é a semente para uma análise de padrões de busca e navegação em páginas de projetos da wikimedia (provavelmente wikipedia).

O [exercício original de análise](https://github.com/wikimedia-research/Discovery-Hiring-Analyst-2016) é um problema proposto pela Wikimedia "for candidates applying to be a Data Analyst in the Discovery department at Wikimedia Foundation." O README do projeto original descreve as análises pedidas aos interessados na posição.

# Report e Objetivo da Atividade

Os dados deste repositório, foram coletados com duração de um pouco mais de uma semana, e são provenientes de um modelo de rastreamento que a [Wikimedia Foundation](https://grafana.wikimedia.org/dashboard/db/eventlogging-schema) usa para avaliar o nível de satisfação do usuário. Os computadores dos usuários são rastreados anonimamente e atoriamente por um esquema que usa um sistema de *ping* a esse computador(es) para estimar por quanto tempo os usuários permanecem nas páginas que visitam. 

O objetivo deste laboratório é analisar os dados do registro de eventos para rastrear uma variedade de métricas de desempenho:

**Taxa de cliques**: a proporção de sessões da pesquisa em que o usuário clicou em um dos resultados exibidos.

**Taxa de resultados zero**: a proporção de pesquisas que resultaram em zero resultados.

## Organização

`code`: código para importar + transformar dados para análise, código de funções úteis em mais de um ponto.

`data`: dados criados para essa análise.

`reports`: notebooks das análises.

## Dependências

R, com os pacotes `tidyverse`, `lubridate`, `scales`, `knitr` e `here`.

# Conclusões

Após a exploração dos dados do Wimedia Foundation, verificamos a influência da taxa de clique em oito dias para dois grupos diferentes. Algumas conclusões podem ser verificadas:

1. O CRT do grupo A é maior do que o grupo B, e o fato pode ser influenciado pela taxa de zero resultados (ZRR) que é  maior no grupo B relacionado ao grupo A. Ou seja, se não houve resultados, consequentemente não é apresentado uma taxa alta de cliques.

2. O tempo médio das sessões é maior no grupo A do que no grupo B. Esse fato também está diretamente relacionado ao CRT e ao ZRR. os usuários tendem a passar mais tempo nas sessões se elas apresentam resultados, pois elas teriam mais opções de visualização das páginas. Já para os zeros resultados, se não é apresentado resultado, o tempo de sessão tende a ser menor, pois o usuário perde o interesse na página e tende a procurar outras alternativas de busca.

3. A maioria das pessoas clicaram no primeiro resultado apresentado. Pesquisas afirmam que os resultados [número 1](https://viverdeblog.com/7-passos-mais-trafego/) tendem a receber mais visitas. Consequentemente deve ter alguma relação entre o tamanho da sessão e o primeiro clique. Essa hipótese deverá ser analisada em trabalhos futuros.

4. Relacionada ao tamanho das sessões, os usuários do grupo B gastaram menos tempo do que o grupo A. Uma hipótese é que as pesquisas do grupo A sejam mais relevantes do que o do grupo B, uma vez que os zeros resultados são menores e a taxa de clique é maior. O grupo B também apresentou um alto índice de sessões em até 10 segundos. Isso pode ratificar a hipótese sobre o grupo B de apresentar pesquisas menos relevantes. Ou mesmo na verificação de uma pesquisa que tenha alguma relação com o termo pesquisado, o usuário B clique na página apenas para verificar se o que foi procurado encontra-se na página clicada.

Há ainda outros fatores que podem ser descobertos com uma segunda análise. Esses fatores serão explorados em trabalhos futuros.
