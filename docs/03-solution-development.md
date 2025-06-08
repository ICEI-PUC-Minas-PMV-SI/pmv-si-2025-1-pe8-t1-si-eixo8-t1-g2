# 3. DESENVOLVIMENTO DE ALTERNATIVAS DE SOLUÇÕES DE SI

## 3.1. Conexão com o Plano de IC  e Planejamento da Solução

A solução proposta é um sistema de Business Intelligence (BI), desenvolvido por meio da ferramenta Power BI. Essa solução tem como objetivo transformar os dados operacionais da empresa Electronic Games Assistência Técnica em informações estratégicas, por meio da criação de dashboards interativos e indicadores de desempenho. 

O foco principal da solução será responder a questões estratégicas definidas no Plano de Inteligência Competitiva (IC), especialmente aquelas relacionadas à previsibilidade dos prazos de manutenção e à eficiência operacional.

A solução permitirá analisar o tempo médio de reparo por tipo de defeito e equipamento, identificar gargalos no processo de assistência técnica, acompanhar a produtividade da equipe técnica e avaliar a disponibilidade e o giro de estoque.

## 3.1.1. Seleção de KIQs a serem inseridos no dashboard

A partir da lista de KIQs definidas no plano de IC, foram selecionadas aquelas com maior relevância operacional e impacto direto na previsibilidade dos prazos de manutenção — tema central do projeto. As perguntas abaixo nortearão a criação do dashboard:

| KIQ | Pergunta |
| ---- | ------ |
| KIQ-01 | Qual é o tempo médio de execução dos diferentes tipos de serviço? | 
| KIQ-02 | Qual é o tempo médio de execução dos diferentes tipos de equipamento? | 
| KIQ-03 | Qual é o tempo médio de espera do cliente desde o recebimento até a entrega do videogame? | 
| KIQ-04 | Qual é a variação do tempo médio de reparo entre diferentes tipos de consoles e defeitos? | 
| KIQ-05 | Quais são os principais motivos de retrabalho nos reparos e como reduzi-los? | 
| KIQ-06 | Como a distribuição das tarefas entre os técnicos impacta o tempo médio de reparo? | 
| KIQ-19 | Qual é o Tempo Médio de Reparação (TMR)? | 
| KIQ-20 | Qual é a Taxa de Retrabalho (TR)? | 
| KIQ-22 | Quantos reparos cada técnico conclui por período (NRCT)? | 

Essas perguntas servem como ponto de partida para identificar gargalos operacionais, mensurar a eficiência dos serviços prestados e analisar o desempenho da equipe técnica. Além disso, as KIQs que não foram selecionadas como prioritárias — mas que também fazem parte do plano de IC — poderão ser inseridas ou aglutinadas sempre que necessário, com o objetivo de aprofundar a análise e gerar insights mais qualitativos que fortaleçam o processo decisório da organização.

## 3.1.2. Definição das fontes de dados internas e externas

As principais fontes de dados da solução de Business Intelligence são internas, provenientes do sistema ERP proprietário da Electronic Games BH. Este sistema foi desenvolvido em C# com banco de dados relacional MySQL, gerenciado por meio da ferramenta Navicat 8. A estrutura do banco é composta por 27 tabelas inter-relacionadas, organizadas nos domínios operacional, cadastral, financeiro e de governança.

Essas tabelas reúnem informações essenciais para as análises, como: 

- Ordens de serviço (O.S.); 
- Tipos de defeito e equipamentos atendidos; 
- Datas de recebimento, diagnóstico, reparo e entrega; 
- Dados dos técnicos responsáveis; 
- Histórico de retrabalho e aprovação de orçamento; 
- Controle de estoque e movimentação de peças.

Devido às limitações do sistema vigente, a coleta de dados foi realizada, inicialmente, por meio da exportação manual de arquivos .csv diretamente do sistema via Navicat 8. 

A estratégia de armazenamento dos dados seguiu a estrutura descrita na Tabela 2 – Estratégia de armazenamento de dados, baseada no conceito de arquitetura em camadas (medallion architecture). Os dados extraídos foram armazenados inicialmente no Azure Data Lake Storage (camada bruta) e, posteriormente, transformados nas camadas inicial e intermediária com o uso do dbt (Data Build Tool).

A camada analítica (mart) foi conectada diretamente ao Power BI, que passou a consumir os dados já tratados para fins de visualização e análise interativa. Essa abordagem garantiu rastreabilidade, governança e eficiência no tratamento e exploração das informações.

## 3.1.3. Relacionamento entre métricas, indicadores e objetivos de negócio

As métricas e indicadores definidos para a solução de BI estão diretamente relacionados às Key Intelligence Questions (KIQs) priorizadas no plano de Inteligência Competitiva, as quais refletem as necessidades estratégicas da Electronic Games BH. 

Entre os principais indicadores a serem monitorados estão:

- Tempo Médio de Reparação (TMR);
- Taxa de Retrabalho Técnico;
- Produtividade da Equipe (reparos por técnico);
- Taxa de Conversão de Orçamentos;
- Taxa de Ruptura de Estoque.

Esses indicadores serão calculados a partir de dados transacionais extraídos do ERP, tratados e modelados com o uso da ferramenta dbt (Data Build Tool), e visualizados no Power BI por meio de dashboards interativos. A escolha dessas ferramentas visa garantir padronização, rastreabilidade e clareza na geração de insights.

## 3.2. Organização e Modelagem de Dados

## 3.2.1. Organização dos dados

Os dados utilizados na solução foram extraídos manualmente do sistema ERP da Electronic Games BH por meio da exportação de arquivos no formato .csv. Esses arquivos foram, então, carregados em um banco de dados SQL estruturado e hospedado na plataforma Azure, garantindo um ambiente seguro, escalável e compatível com ferramentas modernas de modelagem e análise de dados.

Essa base centralizada possibilitou a aplicação de boas práticas de organização e modelagem, viabilizando a criação de uma camada intermediária de dados já preparados para consumo analítico. A planilha compartilhada no Google Sheets foi utilizada paralelamente como um recurso de apoio para o mapeamento das perguntas analíticas e variáveis de interesse, mas não representa a estrutura real da base de dados utilizada na modelagem.

## 3.2.2. Mapeamento de variáveis, filtros e categorias relevantes

Foi realizado um mapeamento completo das variáveis disponíveis em cada tabela, identificando:

- **Métricas quantitativas**: como quantidade de serviços, tempo de reparo, valor de orçamento, valor de venda, etc;
- **Atributos categóricos**: como tipo de defeito, status da O.S., marca e modelo de equipamento, status de pagamento, entre outros;
- **Dimensões de análise**: como cliente, técnico, data, tipo de produto, canal de atendimento.

Esse mapeamento permitiu definir quais campos serão utilizados como dimensões analíticas, filtros interativos e indicadores-chave de desempenho (KPIs) nos painéis do Power BI. Além disso, foram identificadas variáveis que exigem normalização (ex: padronização de status ou tipos de defeito) e tratamento de nulos ou duplicidades, como parte do processo de limpeza e transformação posterior.

## 3.2.3. Validação da consistência e qualidade dos dados

Antes de iniciar a modelagem analítica, os dados foram submetidos a uma etapa de validação para garantir sua integridade e consistência. As seguintes verificações foram realizadas:

- **Checagem de duplicidades** em chaves primárias e registros críticos (ex: IDs de ordens de serviço e de clientes);
- **Verificação de relacionamentos entre tabelas**, garantindo a integridade referencial entre fatos e dimensões;
- **Análise de valores nulos** ou inconsistentes em campos essenciais (ex: datas ausentes, técnicos não vinculados à O.S., valores negativos inválidos);
- **Validação cruzada** entre colunas relacionadas (ex: se a data de entrega da O.S. é posterior à de abertura, se o valor total da venda corresponde à soma dos itens, etc.).

## 3.3. Planejamento dos Dashboards

O planejamento dos dashboards foi orientado pelos Key Performance Indicators (KPIs) definidos previamente com base nas Key Intelligence Questions (KIQs) estabelecidas no plano de Inteligência Competitiva (IC). Esses KPIs incluem, entre outros, o **Tempo Médio de Reparação**, a **Taxa de Retrabalho** e a **Taxa de Conversão de Orçamentos**, que fornecem subsídios essenciais para o monitoramento da performance operacional e da qualidade dos serviços prestados.

## 3.3.1. Planejamento das visualizações com base nos KPIs

A escolha dos gráficos será feita com base no tipo de dado a ser apresentado e na melhor forma de facilitar a interpretação por parte dos gestores e da equipe técnica. 

Cada KPI será transformado em gráficos específicos, tais como:
- **Gráficos de linha** para análise de tendências (ex.: volume de reparos ao longo do tempo).
- **Gráficos de barras** para comparações entre categorias, como a eficiência de técnicos ou a frequência de tipos de defeitos.
- **Gráficos de pizza** para visualização de distribuições percentuais, como a participação de peças no estoque.
- **Tabelas dinâmicas** para detalhamento de dados com capacidade de drill-down, permitindo que o usuário aprofunde a análise.

## 3.3.2. Identificação de filtros e recursos interativos

Além dos gráficos, será importante planejar os filtros e elementos interativos que permitirão aos usuários personalizar as visualizações conforme suas necessidades. Filtros serão aplicados para segmentar os dados por variáveis chave, como:

- **Data (meses, trimestres, anos)** para análise temporal;
- **Técnicos** para comparar o desempenho individual;
- **Peças e tipos de defeito** para aprofundar a análise dos reparos;
- **Status de OS (em andamento, concluída, pendente)** para controle do fluxo de trabalho.

Esses filtros permitirão que os usuários interajam com os dashboards de forma dinâmica, extraindo insights mais específicos de acordo com suas necessidades. Além disso, será planejada a implementação de funcionalidades de drill-down, permitindo aos usuários visualizar os detalhes dos dados, como o histórico de reparos de um técnico ou os tipos de defeitos em um período específico.

## 3.3.3. Validação da estrutura com base nos objetivos de IC

A validação da estrutura dos dashboards foi realizada com base nos objetivos definidos no plano de Inteligência Competitiva (IC), assegurando que os indicadores e visualizações desenvolvidos respondam de forma direta e eficaz às Key Intelligence Questions (KIQs) previamente estabelecidas. Para isso, será feito um alinhamento entre as visualizações propostas e os objetivos da empresa, como:

- **Eficiência operacional**: Acompanhamento de KPIs como o tempo médio de reparo e a taxa de retrabalho para identificar áreas de melhoria.
- **Gestão de recursos**: Avaliação de KPIs como a disponibilidade de peças e o uso dos técnicos, garantindo que os recursos estejam alocados de maneira eficiente.
- **Gestão financeira**: Análise de KPIs financeiros, como o fluxo de caixa relacionado às ordens de serviço e vendas.

Essa validação garante que os dashboards não apenas informem, mas cumpram um papel ativo na geração de vantagem competitiva para a Electronic Games, por meio de análises orientadas à ação e alinhadas aos desafios estratégicos do negócio.

## 3.4. Construção e automação do dashboard

O dashboard foi projetado com o objetivo de atender às principais Key Intelligence Questions (KIQs) definidas no Plano de Inteligência Competitiva (IC), com ênfase na previsibilidade dos prazos de manutenção, na análise da produtividade da equipe técnica e no controle da taxa de retrabalho. A construção foi realizada na ferramenta Power BI, com base em dados extraídos do sistema ERP proprietário da empresa, conforme o modelo dimensional estruturado previamente.

## 3.4.1. Implementação da conexão com as fontes de dados

A conexão com as fontes de dados foi estabelecida a partir da exportação manual de arquivos no formato .csv, extraídos diretamente do banco de dados MySQL, por meio da ferramenta Navicat 8. Esses arquivos foram armazenados em um data lake estruturado na plataforma Azure, e posteriormente transformados utilizando a ferramenta dbt (Data Build Tool), com aplicação de regras de negócios, padronização de nomenclaturas e limpeza de inconsistências.

A camada analítica resultante foi consumida pelo Power BI, permitindo a construção de um dashboard com visualizações dinâmicas e múltiplos filtros. A arquitetura utilizada seguiu o modelo em camadas (medallion architecture).

## 3.4.2. Visualização principal e estrutura de navegação

O dashboard foi dividido em duas páginas principais: Serviço e Produção, com navegação implementada por meio de botões na parte superior da interface. Ambas as páginas apresentam painéis com visualizações gráficas, indicadores de desempenho e filtros laterais (ano, mês, serviço, aparelho e técnico), possibilitando uma análise segmentada por período, por tipo de serviço ou por técnico responsável.

## 3.4.2.1. Serviço

A página Serviço concentra os indicadores relacionados ao tempo de execução, atendimento e reparação, bem como à taxa de retrabalho.

**Indicadores de performance (cards superiores):**
- Tempo médio de execução por serviço;
- Tempo médio de espera do cliente;
- Tempo médio de reparo;
- Tempo médio de atendimento inicial;
- Taxa de retrabalho (%).

**Visualizações detalhadas:**
- Gráficos de barras horizontais para análise do tempo médio de execução por tipo de serviço e equipamento;
- Gráficos de tempo médio de reparo por serviço e por equipamento;
- Gráficos de barras horizontais para análise do tempo médio de atendimento inicial por serviço e técnico;
- Gráfico de pizza representando o tempo médio de atendimento inicial por tipo serviço ou garantia;
- Gráfico de barras com a taxa de retrabalho por equipamento.

![Figura 3 - Interface da página Serviço]()
Figura 3 - Interface da página “Serviço”. 

## 3.4.2.1. Produção

A página Produção apresenta métricas voltadas ao desempenho da equipe técnica na fase de orçamento e diagnóstico.

Indicadores principais:
Tempo médio de orçamento;
Taxa de aprovação de orçamentos;
Taxa de conversão de orçamento;
Taxa média de diagnóstico.

Visualizações complementares:
Gráfico de pizza comparando o tempo médio de orçamento por tipo de serviço;
Gráfico de pizza comparando a taxa de aprovação de orçamento por tipo;
Tabela com tempo médio de orçamento e taxa de aprovação por equipamento;
Gráfico de barras com taxa de conversão de orçamento por técnico;
Gráfico de barras com tempo médio de diagnóstico por técnico;
Gráfico de barras vertical com a quantidade de reparos realizados por técnico ao longo do tempo.


Figura 4 - Interface da página “Produção”. 

## 3.4.3. Validação dos dados e testes de visualização

## 3.5. Análise das informações apresentadas nos dashboards
A análise do dashboard permite observar variações no desempenho da empresa na comparação entre os dois últimos anos completos, 2023 e 2024.
3.5.1. Comparação entre os anos de 2023 e 2024
A análise comparativa entre os indicadores operacionais da Electronic Games BH nos anos de 2023 e 2024 permite identificar evoluções relevantes nos processos da empresa, bem como desafios persistentes relacionados à qualidade e à eficiência dos serviços prestados.


Figura 5 - Interface da página “Serviço” com filtro aplicado para o ano de 2023.


Figura 6 - Interface da página “Serviço” com filtro aplicado para o ano de 2024.


Figura 7 - Indicadores com filtro aplicado para o ano de 2023. 

Figura 8 - Indicadores com filtro aplicado para o ano de 2024.


Figura 9 - Tempo Médio de Execução por Serviço e Equipamento com filtro aplicado para o ano de 2023.


Figura 10 - Tempo Médio de Execução por Serviço e Equipamento com filtro aplicado para o ano de 2024.

Figura 11 - Tempo Médio de Reparo por Serviço e Equipamento com filtro aplicado para o ano de 2023.


Figura 12 - Tempo Médio de Reparo por Serviço e Equipamento com filtro aplicado para o ano de 2024. 

Figura 13 - Tempo Médio de Atendimento Inicial por Serviço e Técnico com filtro aplicado para o ano de 2023.


Figura 14 - Tempo Médio de Atendimento Inicial por Serviço e Técnico com filtro aplicado para o ano de 2024.


Figura 15 - Tempo Médio de Atendimento Inicial por tipo de serviço com filtro aplicado para o ano de 2023.


Figura 16 - Tempo Médio de Atendimento Inicial por tipo de serviço com filtro aplicado para o ano de 2024.


Figura 17 - Taxa de retrabalho por equipamento com filtro aplicado para o ano de 2023.



Figura 18 - Taxa de retrabalho por equipamento com filtro aplicado para o ano de 2024.

Inicialmente, observa-se um aumento no Tempo Médio de Execução por Serviço, que passou de 1,69 dias em 2023 para 2,03 dias em 2024, representando um acréscimo de aproximadamente 20,1%. Essa variação pode ser explicada pela maior complexidade média dos serviços realizados no segundo período, destacando-se a presença de ordens de serviço com tempos atípicos, como a “Recuperação da Placa de Vídeo do PlayStation 2”, que registrou 141,67 dias. Tais valores extremos sugerem dificuldades pontuais, possivelmente relacionadas à disponibilidade de peças ou à complexidade do diagnóstico.
Apesar desse aumento no tempo de execução, outros indicadores demonstram melhorias significativas. O Tempo Médio de Espera do Cliente apresentou uma redução de 5,31 dias para 4,54 dias (queda de 14,5%), evidenciando avanços na gestão da fila de serviços e no cumprimento de prazos de entrega. Esse resultado também está alinhado à expressiva redução no Tempo Médio de Atendimento Inicial, que caiu de 3,40 dias em 2023 para 2,22 dias em 2024, o que representa um ganho de eficiência superior a 34%. Essa melhoria sugere maior agilidade nas etapas de recepção, triagem e diagnóstico inicial dos equipamentos.
O Tempo Médio de Reparo manteve-se relativamente estável entre os dois anos, passando de 0,43 para 0,46 dias, o que indica consistência na execução dos serviços técnicos propriamente ditos. Essa estabilidade é positiva, sobretudo quando considerada em conjunto com a melhora no atendimento inicial e na entrega ao cliente.
No entanto, a Taxa de Retrabalho apresentou um leve aumento, variando de 8,34% em 2023 para 8,59% em 2024. Embora essa diferença não seja expressiva em termos percentuais, ela revela que há oportunidades de aprimoramento nos procedimentos técnicos. Em especial, a análise por equipamento revelou uma alta taxa de retrabalho associada ao PlayStation 3 Slim, com 20% em 2024. O mesmo ocorreu com o Xbox 1, cuja taxa aumentou de 8,91% para 15,09%. Tais aumentos sinalizam a necessidade de revisão técnica aprofundada nos serviços prestados a esses modelos, bem como possível reforço em treinamentos específicos para os técnicos responsáveis.


Figura 19 - Interface da página “Produção” com filtro aplicado para o ano de 2023.



Figura 20 - Interface da página “Produção” com filtro aplicado para o ano de 2024.


Figura 21 - Indicadores com filtro aplicado para o ano de 2023.


Figura 22 - Indicadores com filtro aplicado para o ano de 2024.


Figura 23 - Tempo Médio de Orçamento por tipo com filtro aplicado para o ano de 2023.

Figura 24 - Tempo Médio de Orçamento por tipo com filtro aplicado para o ano de 2024.


Figura 25 - Tempo médio de diagnóstico por técnico com filtro aplicado para o ano de 2023.

Figura 26 -  Tempo médio de diagnóstico por técnico com filtro aplicado para o ano de 2024.


Figura 27 - Quantidade de reparo por técnico e período com filtro aplicado para o ano de 2023.


Figura 28 - Quantidade de reparo por técnico e período com filtro aplicado para o ano de 2024.

Além dos indicadores relacionados ao serviço, a aba “Produção” apresenta métricas essenciais sobre orçamento, diagnóstico e volume de produção por técnico. A análise comparativa entre os anos de 2023 e 2024 revela avanços substanciais no desempenho operacional da Electronic Games, especialmente no que se refere à agilidade dos processos.
O Tempo Médio de Orçamento (TMO) teve uma redução significativa, passando de 3,58 dias em 2023 para 2,73 dias em 2024, o que representa uma melhoria de aproximadamente 23,7%. Esta evolução indica maior eficiência na elaboração e entrega dos orçamentos aos clientes, o que tende a impactar positivamente a percepção de qualidade e a agilidade percebida no atendimento.
De maneira semelhante, o Tempo Médio de Diagnóstico (TMD) apresentou leve aumento, variando de 0,60 para 0,67 dias. Apesar dessa elevação, o tempo permanece dentro de parâmetros operacionais satisfatórios e pode estar associado a uma ampliação no volume ou na diversidade de serviços processados, conforme apontado nos gráficos de produção por técnico.
Importante destacar que tanto a Taxa de Aprovação de Orçamentos quanto a Taxa de Conversão por Técnico mantiveram-se em 100% em ambos os anos. Este resultado reforça a adequação das propostas de orçamento aos critérios dos clientes.
Ao analisar o tempo médio de orçamento por tipo, observa-se que os serviços de garantia demandaram mais tempo que os serviços comuns em ambos os anos, embora também tenham apresentado redução: de 3,96 dias em 2023 para 3,10 dias em 2024. Isso sugere maior uniformização dos processos, mesmo em categorias com critérios de atendimento diferenciados.
O detalhamento por equipamento revela algumas variações relevantes. Em 2023, equipamentos como o PlayStation 2 Slim e o Wii demandaram os maiores tempos médios de orçamento, com 7,25 e 4,47 dias, respectivamente. Já em 2024, a média do PlayStation 2 subiu para 5,65 dias, tornando-se o item com maior TMO do ano. Isso pode sinalizar desafios específicos relacionados à análise técnica desses modelos, como escassez de peças ou necessidade de procedimentos mais elaborados.
No que tange ao desempenho individual dos técnicos, é possível perceber uma maior homogeneidade no tempo médio de diagnóstico em 2024 quando comparado a 2023. Por exemplo, o técnico V. J. N. de S., que em 2023 registrou tempo médio de 1,6 dias, reduziu significativamente sua média em 2024. Técnicos como J. A. da S. e F. P. S. continuam a apresentar desempenhos consistentes, com tempos inferiores a um dia para conclusão de diagnósticos.
Quanto à quantidade de reparos por técnico ao longo do tempo, os gráficos revelam uma variação importante na produtividade mensal. Destaca-se, em 2024, o crescimento da produção de C. de A. S., com picos superiores a 100 reparos mensais. Esse desempenho reforça a hipótese de amadurecimento da equipe e melhor distribuição das tarefas técnicas.
De modo geral, os indicadores da aba Produção apontam para melhorias consistentes na agilidade dos processos de orçamento e diagnóstico, associadas à manutenção de altas taxas de aprovação e conversão.
3.5.2. Comparação entre os primeiros meses de 2024 e 2025
A análise comparativa dos indicadores operacionais referentes aos primeiros meses dos anos de 2024 e 2025 revela mudanças significativas nos padrões de execução, produtividade técnica e qualidade dos serviços prestados pela Electronic Games BH. Essa comparação permite avaliar tendências recentes e antecipar possíveis pontos de atenção para os próximos ciclos operacionais.


Figura 29 - Interface da página “Serviço” com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024. 

Figura 30 - Interface da página “Serviço” com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.


Figura 31 - Indicadores com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024.


Figura 32 - Indicadores com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.


Figura 33 -  Tempo Médio de Execução por Serviço e Equipamento com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024.


Figura 34 - Tempo Médio de Execução por Serviço e Equipamento com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.


Figura 35 - Tempo Médio de Reparo por Serviço e Equipamento com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024. 

Figura 36 -Tempo Médio de Reparo por Serviço e Equipamento com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.


Figura 37 - Tempo Médio de Atendimento Inicial por Serviço e Técnico com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024.


Figura 38 -Tempo Médio de Atendimento Inicial por Serviço e Técnico com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.


Figura 39 - Tempo Médio de Atendimento Inicial por tipo de serviço com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024.


Figura 40 - Tempo Médio de Atendimento Inicial por tipo de serviço com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.

Figura 41 - Taxa de retrabalho por equipamento com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024.


Figura 42 - Taxa de retrabalho por equipamento com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.

O Tempo Médio de Execução por Serviço apresentou um aumento considerável, passando de 1,59 dias em 2024 para 2,33 dias em 2025. Esse acréscimo de aproximadamente 46,5% sugere um aumento na complexidade dos serviços realizados, hipótese corroborada pelos dados sobre tipos de serviço, em que há destaque para reparos de longa duração, como a “Mão de Obra troca da Unidade Óptica PS2 Slim - PVR-802” (17,40 dias) e “Mão de obra troca da roldana (LOJ)” (11,33 dias).
Em relação ao Tempo Médio de Espera do Cliente, também houve um crescimento expressivo, saltando de 4,69 dias para 6,05 dias (cerca de 29,1% de aumento). Essa elevação pode indicar um acúmulo de ordens de serviço em fila ou uma maior demanda de atendimento sem contrapartida de ampliação da capacidade operacional. Esse cenário pode impactar negativamente a experiência do cliente, sugerindo a necessidade de ações corretivas na triagem e na alocação de tarefas.
No que diz respeito ao Tempo Médio de Reparo, o indicador praticamente dobrou, de 0,40 dias em 2024 para 0,71 dias em 2025. Esse comportamento, combinado com o aumento do tempo de execução, reforça a hipótese de que os reparos passaram a exigir maior esforço técnico, seja por evolução tecnológica dos equipamentos, maior taxa de casos complexos ou desafios logísticos, como reposição de peças.
O Tempo Médio de Atendimento Inicial também sofreu elevação, subindo de 2,91 dias para 3,76 dias. Isso representa um aumento de 29,2%, sinalizando gargalos nas etapas iniciais de recepção e diagnóstico. Técnicos como F. P. S., que apresentava média de 4,98 dias no início de 2024, chegaram a 6,23 dias no mesmo período de 2025, indicando uma sobrecarga de atividades ou falta de automação nos processos iniciais.
A Taxa de Retrabalho passou de 8,97% para 10,01%, configurando um alerta importante. Esse crescimento, embora aparentemente discreto, representa uma piora na qualidade técnica dos reparos, sobretudo quando observamos a taxa por equipamento. O destaque negativo fica para o Dreamcast, que em 2025 registrou uma taxa de retrabalho de 50%, seguido pelo Xbox 1 (12,82%) e PlayStation 3 (12,67%). A reincidência de falhas nesses modelos reforça a necessidade de revisar os procedimentos técnicos específicos para tais consoles, incluindo eventuais ações de capacitação ou revisão de protocolos de testes.
Por outro lado, ainda que os indicadores de tempo e qualidade tenham se deteriorado no comparativo entre os primeiros meses dos dois anos, é importante ressaltar que os dados não apontam para uma queda abrupta ou descontrole do processo, mas sim para uma tendência de crescimento na demanda e na complexidade dos serviços. Diante disso, a empresa deve agir de forma preventiva, antecipando melhorias na distribuição de tarefas, na priorização de atendimentos e na capacitação contínua da equipe técnica.


Figura 43 - Interface da página “Produção” com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024. 


Figura 44 - Interface da página “Produção” com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.


Figura 45 - Interface da página “Produção” com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024. 


Figura 46 - Interface da página “Produção” com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.


Figura 47 - Tempo Médio de Orçamento por tipo com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024. 


Figura 48 - Tempo Médio de Orçamento por tipo com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.

Figura 49 - Interface da página “Produção” com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024. 

Figura 50 - Interface da página “Produção” com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.

Figura 51 - Interface da página “Produção” com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024. 


Figura 52 - Interface da página “Produção” com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.

A análise dos indicadores da aba Produção revela diferenças importantes no desempenho operacional da Electronic Games BH entre os quatro primeiros meses dos anos de 2024 e 2025.
O Tempo Médio de Orçamento (TMO) aumentou de 3,40 dias em 2024 para 4,13 dias em 2025, o que representa um acréscimo de aproximadamente 21,5%. Esse aumento pode estar relacionado ao maior volume de ordens de serviço com garantia no início de 2025 — conforme indicado pelo gráfico de tempo médio por tipo — em que os serviços de garantia demandaram 4,77 dias, frente a 3,41 dias em 2024. Essa diferença pode indicar a existência de procedimentos internos mais burocráticos para orçamentos sob garantia, impactando negativamente na agilidade de resposta ao cliente.
O Tempo Médio de Diagnóstico também sofreu uma leve elevação, passando de 0,49 dias para 0,55 dias, o que sugere uma tendência de crescimento moderado no tempo necessário para análise técnica inicial. Ainda que a diferença seja discreta, sua manutenção ao longo dos meses pode indicar a necessidade de revisão dos fluxos de trabalho ou ampliação da equipe envolvida nas etapas diagnósticas.
Em contrapartida, a Taxa de Aprovação de Orçamentos e a Taxa de Conversão por Técnico mantiveram-se em 100% em ambos os períodos analisados. Esse resultado denota consistência nos critérios de precificação e clareza nas comunicações com os clientes, além de demonstrar uniformidade na abordagem da equipe técnica, independentemente do aumento na complexidade dos serviços.
No detalhamento por equipamento, o tempo médio de orçamento para consoles como o PlayStation Portátil e o Xbox 360 apresentou crescimento expressivo. O Xbox 360, por exemplo, passou de 4,35 dias em 2024 para 5,82 dias em 2025. Essa elevação reforça a hipótese de aumento da complexidade média dos orçamentos emitidos, o que pode estar associado à escassez de peças, necessidade de avaliações mais detalhadas ou maior número de serviços sob garantia.
No que tange à produtividade técnica, verifica-se que a maioria dos colaboradores apresentou aumento na quantidade de reparos mensais. Técnicos como F. P. S., e P. H. M. ultrapassaram a marca de 100 reparos mensais em diferentes períodos de 2025, o que aconteceu poucas vezes em 2024.

## 3.5.3. Recomendações sugeridas com base nas análises

Com base nas análises geradas pelos dashboards, foram elaboradas as seguintes recomendações:
Revisão do processo de diagnóstico inicial, identificando possíveis melhorias para reduzir o Tempo Médio de Atendimento Inicial (TMAI); 
Por que essa melhoria é importante: o Tempo Médio de Atendimento Inicial aumentou significativamente de 2,91 dias em 2024 para 3,76 dias em 2025;
Realização de uma auditoria interna no fluxo de atendimento inicial para visualização dos pontos específicos que estão causando atrasos;
Considerar o uso de ferramentas tecnológicas ou aplicativos para cadastro rápido em que seja possível fazer um acompanhamento em tempo real das ordens de serviço e do tempo gasto em cada etapa;
Estabelecer um padrão rigoroso para que seja dado prioridade no atendimento de dispositivos com maior volume de serviços ou maior complexidade;
Melhorias na gestão da fila de espera;
Por que essa melhoria é importante: ocorreu um aumento expressivo no Tempo Médio de Espera do Cliente, que subiu de 4,69 dias (2024) para 6,05 dias (2025);
Implementar um serviço de notificações automatizadas para os clientes. Assim os clientes conseguirão acompanhar em tempo real o status de reparo;
Considerar a adoção de agendamento de serviços com uma pré-avaliação remota, caso seja possível, a fim de diminuir o tempo que um equipamento permanece na fila;
Redução no Tempo Médio de Reparo;
Por que essa melhoria é importante: o Tempo Médio de Reparo cresceu de 0,40 dias em 2024 para 0,71 dias em 2025;
Desenvolvimento de treinamentos específicos voltados aos procedimentos complexos identificados no período recente (ex: recuperação de placas);
Oferecer serviço de manutenção preventiva para os equipamentos que apresentam falhas frequentes para os clientes;
Diminuição da Taxa de Retrabalho;
Por que essa melhoria é importante: a Taxa de Retrabalho aumentou de 8,97% em 2024 para 10,01% em 2025;
Fazer uma análise aprofundada dos retrabalhos ocorridos que apresentaram um aumento significativo como PlayStation 3 Slim e Xbox 1;
Criar equipes especializadas ou atribuir técnicos específicos para os equipamentos mais problemáticos;
Desenvolver materiais e guias técnicos específicos para equipamentos que têm apresentado tempos mais elevados de reparo ou altos índices de retrabalho;
Redistribuição de serviços entre técnicos para reduzir a sobrecarga de profissionais com maior número de reparos e melhorar a eficiência geral;
Por que essa melhoria é importante: por conta da variação observada na produtividade individual dos técnicos, destacada na análise que menciona técnicos com desempenho irregular;
Melhorias com base nos resultados gerais do projeto;
Fazer uso de inteligência artificial ou aprendizado de máquina para apoiar diagnósticos preliminares ou monitorar continuamente os indicadores operacionais;
Por que essa melhoria é importante: o aumento generalizado nos indicadores operacionais (Tempo Médio de Atendimento Inicial, Espera, Execução e Reparo) evidencia a necessidade de otimização operacional;
Criar dashboards específicos e detalhados, permitindo uma análise em tempo real dos indicadores e rápida tomada de decisões;
Por que essa melhoria é importante: indicado pela complexidade de acompanhamento contínuo dos indicadores, especialmente pela relevância demonstrada por variações bruscas de um ano para outro.

## 3.6. Viabilidade técnica e financeira da estrutura desenvolvida

	Através da análise, são apresentados os recursos tecnológicos utilizados na solução proposta, acompanhados de uma análise técnica e financeira que demonstra a viabilidade de sua adoção pela empresa.
## 3.6.1. Estrutura Tecnológica Adotada
A arquitetura proposta para o sistema de Business Intelligence contempla três componentes principais:
Armazenamento de dados: Banco de dados relacional MySQL Flexível (Azure).


Transformação de dados: Ferramenta de transformação dbt Core (versão CLI).


Visualização de dados: Power BI Desktop para criação de dashboards locais.


Essa estrutura foi escolhida por sua compatibilidade com a nuvem, escalabilidade progressiva e uso gratuito de ferramentas open-source. Além disso, o volume atual de dados da empresa é relativamente pequeno, com aproximadamente 800MB de dados, o que permite iniciar a operação com uma configuração leve e de baixo custo.

O monitoramento de custo e uso será feito por meio do Azure Cost Management, permitindo ajustes dinâmicos conforme o crescimento do volume de dados e acessos.

## 3.6.2. Justificativa Técnica das Escolhas

Componente
Justificativa Técnica
MySQL Flexível (Azure)
Suporte à escalabilidade, backup automático, alta disponibilidade e integração com ferramentas nativas da Microsoft. A capacidade inicial é suficiente para hospedar os 800MB de dados atuais, com margem para expansão futura.
dbt Core
Ferramenta open-source de transformação de dados com versionamento de modelos e modularidade. Pode ser executada localmente, sem custos adicionais
Power BI Desktop
Solução amplamente adotada para visualização de dados, com alto poder de criação de dashboards e sem custos iniciais de licenciamento. Ideal para análise local de dados.



## 3.6.3. Estimativa de Custo Mensal

Categoria
Recurso/Serviço
Custo Estimado Mensal
Banco de dados
Servidor MySQL flexível implantação, Camada Com capacidade de intermitência, 1 B1MS (1 vCores) x 730 Horas, 1 vCore (B1MS), 5GB de armazenamento, ZRS, sem E/S paga
R$191,98
Transformação
dbt Core CLI (open-source, executado localmente)
Gratuito
Visualização
Power BI Desktop
Gratuito
Total Estimado
R$191,98


## 3.6.4. Escalabilidade e cenários de custo

Cenário de Uso
Estimativa Mensal
Fase atual (dados pequenos, sem E/S)
R$191,98
Operação com 20GB e tráfego moderado
R$ 400,00–R$ 600,00
Crescimento contínuo (com backup e E/S)
R$ 800,00–R$ 1.200,00



## 3.6.5. Conclusão da Viabilidade

A estrutura proposta é tecnicamente sólida, financeiramente viável e escalável. Com um custo mensal inicial inferior a R$200,00, a empresa poderá implantar um sistema de Business Intelligence completo, com visualizações interativas, controle de dados estruturado e possibilidade de crescimento conforme a demanda. Trata-se de uma solução estratégica e sustentável para suportar a evolução operacional da empresa
Eletronic Games.

