### 3. Desenvolvimento de Alternativas de Soluções de SI

#### 3.1. Conexão com o Plano de IC e Planejamento da Solução

A solução proposta é um sistema de Business Intelligence (BI), desenvolvido por meio da ferramenta Power BI. Essa solução tem como objetivo transformar os dados operacionais da empresa em informações estratégicas, por meio da criação de dashboards interativos e indicadores de desempenho. 

O foco principal da solução será responder a questões estratégicas definidas no Plano de Inteligência Competitiva (IC), especialmente aquelas relacionadas à previsibilidade dos prazos de manutenção e à eficiência operacional.

A solução permitirá analisar o tempo médio de reparo por tipo de defeito e equipamento, identificar gargalos no processo de assistência técnica, acompanhar a produtividade da equipe técnica e avaliar a disponibilidade e o giro de estoque.

##### 3.1.1. Seleção de KIQs a serem inseridos no dashboard

A partir da lista de KIQs definidas no plano de IC, foram selecionadas aquelas com maior relevância operacional e impacto direto na previsibilidade dos prazos de manutenção — tema central do projeto. As perguntas abaixo nortearão a criação do dashboard:

| KIQ      | Pergunta                                                                                      |
|----------|-----------------------------------------------------------------------------------------------|
| KIQ-01   | Qual é o tempo médio de execução dos diferentes tipos de serviço?                             |
| KIQ-02   | Qual é o tempo médio de execução dos diferentes tipos de equipamento?                         |
| KIQ-03   | Qual é o tempo médio de espera do cliente desde o recebimento até a entrega do videogame?     |
| KIQ-04   | Qual é a variação do tempo médio de reparo entre diferentes tipos de consoles e defeitos?     |
| KIQ-05   | Quais são os principais motivos de retrabalho nos reparos e como reduzi-los?                  |
| KIQ-06   | Como a distribuição das tarefas entre os técnicos impacta o tempo médio de reparo?            |
| KIQ-19   | Qual é o Tempo Médio de Reparação (TMR)?                                                      |
| KIQ-20   | Qual é a Taxa de Retrabalho (TR)?                                                             |
| KIQ-22   | Quantos reparos cada técnico conclui por período (NRCT)?                                      |

Essas perguntas servem como ponto de partida para identificar gargalos operacionais, mensurar a eficiência dos serviços prestados e analisar o desempenho da equipe técnica. Além disso, as KIQs que não foram selecionadas como prioritárias — mas que também fazem parte do plano de IC — poderão ser inseridas ou aglutinadas sempre que necessário, com o objetivo de aprofundar a análise e gerar insights mais qualitativos que fortaleçam o processo decisório da organização.

##### 3.1.2. Definição das fontes de dados internas e externas

As principais fontes de dados da solução de Business Intelligence são internas, provenientes do sistema ERP proprietário da empresa. Este sistema foi desenvolvido em C# com banco de dados relacional MySQL, gerenciado por meio da ferramenta Navicat 8. A estrutura do banco é composta por 27 tabelas inter-relacionadas, organizadas nos domínios operacional, cadastral, financeiro e de governança.

Essas tabelas reúnem informações essenciais para as análises, como:

- Ordens de serviço (O.S.);
- Tipos de defeito e equipamentos atendidos;
- Datas de recebimento, diagnóstico, reparo e entrega;
- Dados dos técnicos responsáveis;
- Histórico de retrabalho e aprovação de orçamento;
- Controle de estoque e movimentação de peças.

Devido às limitações do sistema vigente, a coleta de dados foi realizada, inicialmente, por meio da exportação manual de arquivos `.csv` diretamente do sistema via Navicat 8.

A estratégia de armazenamento dos dados seguiu a estrutura descrita na Tabela 2 – Estratégia de armazenamento de dados, baseada no conceito de arquitetura em camadas (medallion architecture). Os dados extraídos foram armazenados inicialmente no Azure Data Lake Storage (camada bruta) e, posteriormente, transformados nas camadas inicial e intermediária com o uso do dbt (Data Build Tool).

A camada analítica (mart) foi conectada diretamente ao Power BI, que passou a consumir os dados já tratados para fins de visualização e análise interativa. Essa abordagem garantiu rastreabilidade, governança e eficiência no tratamento e exploração das informações.

##### 3.1.3. Relacionamento entre métricas, indicadores e objetivos de negócio

As métricas e indicadores definidos para a solução de BI estão diretamente relacionados às Key Intelligence Questions (KIQs) priorizadas no plano de Inteligência Competitiva, as quais refletem as necessidades estratégicas da empresa.

Entre os principais indicadores a serem monitorados estão:

- Tempo Médio de Reparação (TMR);
- Taxa de Retrabalho Técnico;
- Produtividade da Equipe (reparos por técnico);
- Taxa de Conversão de Orçamentos;
- Taxa de Ruptura de Estoque.

Esses indicadores serão calculados a partir de dados transacionais extraídos do ERP, tratados e modelados com o uso da ferramenta dbt (Data Build Tool), e visualizados no Power BI por meio de dashboards interativos. A escolha dessas ferramentas visa garantir padronização, rastreabilidade e clareza na geração de insights.

### 3.2. Organização e Modelagem de Dados

#### 3.2.1. Organização dos dados

Os dados utilizados na solução foram extraídos manualmente do sistema ERP da empresa por meio da exportação de arquivos no formato `.csv`. Esses arquivos foram, então, carregados em um banco de dados SQL estruturado e hospedado na plataforma Azure, garantindo um ambiente seguro, escalável e compatível com ferramentas modernas de modelagem e análise de dados.

Essa base centralizada possibilitou a aplicação de boas práticas de organização e modelagem, viabilizando a criação de uma camada intermediária de dados já preparados para consumo analítico. A planilha compartilhada no Google Sheets foi utilizada paralelamente como um recurso de apoio para o mapeamento das perguntas analíticas e variáveis de interesse, mas não representa a estrutura real da base de dados utilizada na modelagem.

#### 3.2.2. Mapeamento de variáveis, filtros e categorias relevantes

Foi realizado um mapeamento completo das variáveis disponíveis em cada tabela, identificando:

- **Métricas quantitativas**: como quantidade de serviços, tempo de reparo, valor de orçamento, valor de venda, etc;
- **Atributos categóricos**: como tipo de defeito, status da O.S., marca e modelo de equipamento, status de pagamento, entre outros;
- **Dimensões de análise**: como cliente, técnico, data, tipo de produto, canal de atendimento.

Esse mapeamento permitiu definir quais campos serão utilizados como dimensões analíticas, filtros interativos e indicadores-chave de desempenho (KPIs) nos painéis do Power BI. Além disso, foram identificadas variáveis que exigem normalização (ex: padronização de status ou tipos de defeito) e tratamento de nulos ou duplicidades, como parte do processo de limpeza e transformação posterior.

#### 3.2.3. Validação da consistência e qualidade dos dados

Antes de iniciar a modelagem analítica, os dados foram submetidos a uma etapa de validação para garantir sua integridade e consistência. As seguintes verificações foram realizadas:

- Checagem de duplicidades em chaves primárias e registros críticos (ex: IDs de ordens de serviço e de clientes);
- Verificação de relacionamentos entre tabelas, garantindo a integridade referencial entre fatos e dimensões;
- Análise de valores nulos ou inconsistentes em campos essenciais (ex: datas ausentes, técnicos não vinculados à O.S., valores negativos inválidos);
- Validação cruzada entre colunas relacionadas (ex: se a data de entrega da O.S. é posterior à de abertura, se o valor total da venda corresponde à soma dos itens, etc.).

### 3.3. Planejamento dos Dashboards

O planejamento dos dashboards foi orientado pelos Key Performance Indicators (KPIs) definidos previamente com base nas Key Intelligence Questions (KIQs) estabelecidas no plano de Inteligência Competitiva (IC). Esses KPIs incluem, entre outros, o Tempo Médio de Reparação, a Taxa de Retrabalho e a Taxa de Conversão de Orçamentos, que fornecem subsídios essenciais para o monitoramento da performance operacional e da qualidade dos serviços prestados.

#### 3.3.1. Planejamento das visualizações com base nos KPIs

A escolha dos gráficos será feita com base no tipo de dado a ser apresentado e na melhor forma de facilitar a interpretação por parte dos gestores e da equipe técnica. Cada KPI será transformado em gráficos específicos, tais como:

- Gráficos de linha para análise de tendências (ex.: volume de reparos ao longo do tempo);
- Gráficos de barras para comparações entre categorias, como a eficiência de técnicos ou a frequência de tipos de defeitos;
- Gráficos de pizza para visualização de distribuições percentuais, como a participação de peças no estoque;
- Tabelas dinâmicas para detalhamento de dados com capacidade de *drill-down*, permitindo que o usuário aprofunde a análise.

#### 3.3.2. Identificação de filtros e recursos interativos

Além dos gráficos, será importante planejar os filtros e elementos interativos que permitirão aos usuários personalizar as visualizações conforme suas necessidades. Filtros serão aplicados para segmentar os dados por variáveis-chave, como:

- Data (meses, trimestres, anos) para análise temporal;
- Técnicos para comparar o desempenho individual;
- Peças e tipos de defeito para aprofundar a análise dos reparos;
- Status de OS (em andamento, concluída, pendente) para controle do fluxo de trabalho.

Esses filtros permitirão que os usuários interajam com os dashboards de forma dinâmica, extraindo insights mais específicos de acordo com suas necessidades. Além disso, será planejada a implementação de funcionalidades de drill-down, permitindo aos usuários visualizar os detalhes dos dados, como o histórico de reparos de um técnico ou os tipos de defeitos em um período específico.

#### 3.3.3. Validação da estrutura com base nos objetivos de IC

A validação da estrutura dos dashboards foi realizada com base nos objetivos definidos no plano de Inteligência Competitiva (IC), assegurando que os indicadores e visualizações desenvolvidos respondam de forma direta e eficaz às Key Intelligence Questions (KIQs) previamente estabelecidas.

Para isso, será feito um alinhamento entre as visualizações propostas e os objetivos da empresa, como:

- **Eficiência operacional**: Acompanhamento de KPIs como o tempo médio de reparo e a taxa de retrabalho para identificar áreas de melhoria;
- **Gestão de recursos**: Avaliação de KPIs como a disponibilidade de peças e o uso dos técnicos, garantindo que os recursos estejam alocados de maneira eficiente;
- **Gestão financeira**: Análise de KPIs financeiros, como o fluxo de caixa relacionado às ordens de serviço e vendas.

Essa validação garante que os dashboards não apenas informem, mas cumpram um papel ativo na geração de vantagem competitiva para a empresa, por meio de análises orientadas à ação e alinhadas aos desafios estratégicos do negócio.

### 3.4. Construção e automação do dashboard

O dashboard foi projetado com o objetivo de atender às principais Key Intelligence Questions (KIQs) definidas no Plano de Inteligência Competitiva (IC), com ênfase na previsibilidade dos prazos de manutenção, na análise da produtividade da equipe técnica e no controle da taxa de retrabalho. A construção foi realizada na ferramenta Power BI, com base em dados extraídos do sistema ERP proprietário da empresa, conforme o modelo dimensional estruturado previamente.

#### 3.4.1. Implementação da conexão com as fontes de dados

A conexão com as fontes de dados foi estabelecida a partir da exportação manual de arquivos no formato `.csv`, extraídos diretamente do banco de dados MySQL, por meio da ferramenta Navicat 8. Esses arquivos foram armazenados em um data lake estruturado na plataforma Azure, e posteriormente transformados utilizando a ferramenta dbt (Data Build Tool), com aplicação de:

- Regras de negócios;
- Padronização de nomenclaturas;
- Limpeza de inconsistências.

A camada analítica resultante foi consumida pelo Power BI, permitindo a construção de um dashboard com visualizações dinâmicas e múltiplos filtros. A arquitetura utilizada seguiu o modelo em camadas (medallion architecture).

#### 3.4.2. Visualização principal e estrutura de navegação

O dashboard foi dividido em duas páginas principais: Serviço e Produção, com navegação implementada por meio de botões na parte superior da interface.

Ambas as páginas apresentam:

- Painéis com visualizações gráficas;
- Indicadores de desempenho;
- Filtros laterais (ano, mês, serviço, aparelho e técnico);

Esses recursos possibilitam uma análise segmentada por período, por tipo de serviço ou por técnico responsável.

#### 3.4.3. Visualização principal 1 – Serviço

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
- Gráfico de pizza representando o tempo médio de atendimento inicial por tipo de serviço ou garantia;
- Gráfico de barras com a taxa de retrabalho por equipamento.

**Figura 3 - Interface da página Serviço.**

![Figura 3 - Interface da página Serviço](/img/figura-03-interface-pagina-servico.png)

##### 3.4.4. Visualização principal 2 – Produção

A página Produção apresenta métricas voltadas ao desempenho da equipe técnica na fase de orçamento e diagnóstico.

**Indicadores principais:**

- Tempo médio de orçamento;
- Taxa de aprovação de orçamentos;
- Taxa de conversão de orçamento;
- Taxa média de diagnóstico.

**Visualizações complementares:**

- Gráfico de pizza comparando o tempo médio de orçamento por tipo de serviço;
- Gráfico de pizza comparando a taxa de aprovação de orçamento por tipo;
- Tabela com tempo médio de orçamento e taxa de aprovação por equipamento;
- Gráfico de barras com taxa de conversão de orçamento por técnico;
- Gráfico de barras com tempo médio de diagnóstico por técnico;
- Gráfico de barras vertical com a quantidade de reparos realizados por técnico ao longo do tempo.

**Figura 4 – Interface da página Produção.**

![Figura 4 – Interface da página Produção](/img/figura-04-interface-pagina-producao.png)

### 3.5. Análise das informações apresentadas nos dashboards

A análise do dashboard permite observar variações no desempenho da empresa na comparação entre os dois últimos anos completos, 2023 e 2024.

#### 3.5.1. Comparação entre os anos de 2023 e 2024

A análise comparativa entre os indicadores operacionais dos anos de 2023 e 2024 permite identificar evoluções relevantes nos processos da empresa, bem como desafios persistentes relacionados à qualidade e à eficiência dos serviços prestados.

**Figura 5 – Interface da página Serviço com filtro aplicado para o ano de 2023.**  

![Figura 5 - Interface da página Serviço com filtro aplicado para o ano de 2023](/img/figura-05-servico-2023.png)

**Figura 6 – Interface da página Serviço com filtro aplicado para o ano de 2024.**  

![Figura 6 - Interface da página Serviço com filtro aplicado para o ano de 2024](/img/figura-06-servico-2024.png)

Inicialmente, observa-se um aumento no Tempo Médio de Execução por Serviço, que passou de 1,73 dia em 2023 para 2,10 dias em 2024, representando um acréscimo de aproximadamente 21,4%. Essa variação pode ser explicada pela maior complexidade média dos serviços realizados no segundo período, destacando-se a presença de ordens de serviço com tempos atípicos, como a “Recuperação da Placa de Vídeo do PlayStation 2”, que registrou 106,50 dias. Tais valores extremos sugerem dificuldades pontuais, possivelmente relacionadas à disponibilidade de peças ou à complexidade do diagnóstico.

Apesar desse aumento no tempo de execução, outros indicadores demonstram melhorias significativas. O Tempo Médio de Espera do Cliente apresentou uma redução de 5,45 dias para 4,31 dias (queda de 20,9%), evidenciando avanços na gestão da fila de serviços e no cumprimento de prazos de entrega. Esse resultado também está alinhado à expressiva redução no Tempo Médio de Atendimento Inicial, que caiu de 3,37 dias em 2023 para 2,25 dias em 2024, o que representa um ganho de eficiência superior a 33,2%. Essa melhoria sugere maior agilidade nas etapas de recepção, triagem e diagnóstico inicial dos equipamentos.

O Tempo Médio de Reparo manteve-se relativamente estável entre os dois anos, passando de 0,47 para 0,53 dias, o que indica consistência na execução dos serviços técnicos propriamente ditos. Essa estabilidade é positiva, sobretudo quando considerada em conjunto com a melhora no atendimento inicial e na entrega ao cliente.

No entanto, a Taxa de Retrabalho apresentou um leve aumento, variando de 8,35% em 2023 para 8,54% em 2024. Embora essa diferença não seja expressiva em termos percentuais, ela revela que há oportunidades de aprimoramento nos procedimentos técnicos. Em especial, a análise por equipamento revelou uma alta taxa de retrabalho associada ao PlayStation 3 Slim, com 20% em 2024. O mesmo ocorreu com o Xbox 1, cuja taxa aumentou de 9,09% para 15,09%. Tais aumentos sinalizam a necessidade de revisão técnica aprofundada nos serviços prestados a esses modelos, bem como possível reforço em treinamentos específicos para os técnicos responsáveis.

**Figura 7 – Interface da página Produção com filtro aplicado para o ano de 2023.**

![Figura 7 - Interface da página Produção com filtro aplicado para o ano de 2023](/img/figura-07-interface-producao-2023.png)

**Figura 8 – Interface da página Produção com filtro aplicado para o ano de 2024.**

![Figura 8 - Interface da página Produção com filtro aplicado para o ano de 2024](/img/figura-08-interface-producao-2024.png)

Além dos indicadores relacionados ao serviço, a aba Produção apresenta métricas essenciais sobre orçamento, diagnóstico e volume de produção por técnico. A análise comparativa entre os anos de 2023 e 2024 revela avanços substanciais no desempenho operacional da empresa, especialmente no que se refere à agilidade dos processos.

O Tempo Médio de Orçamento (TMO) teve uma redução significativa, passando de 3,56 dias em 2023 para 2,74 dias em 2024, o que representa uma melhoria de aproximadamente 23%. Esta evolução indica maior eficiência na elaboração e entrega dos orçamentos aos clientes, o que tende a impactar positivamente a percepção de qualidade e a agilidade percebida no atendimento.

De maneira semelhante, o Tempo Médio de Diagnóstico (TMD) apresentou leve aumento, variando de 0,60 para 0,67 dias. Apesar dessa elevação, o tempo permanece dentro de parâmetros operacionais satisfatórios e pode estar associado a uma ampliação no volume ou na diversidade de serviços processados, conforme apontado nos gráficos de produção por técnico.

Importante destacar que a Taxa de Aprovação de Orçamentos manteve-se em 100% em ambos os anos. Este resultado reforça a adequação das propostas de orçamento aos critérios dos clientes. Já a Taxa de Conversão de Orçamentos teve uma leve queda de 77,89% em 2023 para 77,12% em 2024.

O detalhamento por equipamento revela algumas variações relevantes. Em 2023, equipamentos como o PlayStation 3 Slim e o Wii apresentaram os maiores tempos médios de orçamento, com 7,25 e 4,48 dias, respectivamente. Já em 2024, o tempo médio de orçamento para esses mesmos equipamentos caiu para 2,20 e 2,16 dias, respectivamente. Enquanto isso, a média do PlayStation 2 aumentou para 5,74 dias, tornando-se o item com maior TMO no ano. Isso pode indicar desafios específicos relacionados à análise técnica desses modelos, como escassez de peças ou necessidade de procedimentos mais complexos.

De modo geral, os indicadores da aba Produção apontam para melhorias consistentes na agilidade dos processos de orçamento e diagnóstico, associadas à manutenção de altas taxas de aprovação e conversão.

#### 3.5.2. Comparação entre os primeiros meses de 2024 e 2025

A análise comparativa dos indicadores operacionais referentes aos primeiros meses dos anos de 2024 e 2025 revela mudanças significativas nos padrões de execução, produtividade técnica e qualidade dos serviços prestados pela empresa. Essa comparação permite avaliar tendências recentes e antecipar possíveis pontos de atenção para os próximos ciclos operacionais.

**Figura 9 – Interface da página Serviço com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024.**  

![Figura 9 - Interface da página Serviço com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024](/img/figura-09-servico-jan-abr-2024.png)

**Figura 10 – Interface da página Serviço com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.**  

![Figura 10 - Interface da página Serviço com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025](/img/figura-10-servico-jan-abr-2025.png)

O Tempo Médio de Execução por Serviço apresentou uma redução considerável, passando de 2,67 dias em 2024 para 1,96 dias em 2025. Essa diminuição de aproximadamente 26,6% pode indicar uma redução na complexidade dos serviços realizados ou melhorias na eficiência operacional.

Em relação ao Tempo Médio de Espera do Cliente, houve uma leve redução, passando de 5,91 dias para 5,82 dias (queda de aproximadamente 1,5%). Embora discreta, essa diminuição pode refletir esforços pontuais na triagem ou na priorização de atendimentos. Ainda assim, recomenda-se atenção contínua à alocação de tarefas para evitar acúmulo de ordens de serviço e preservar a qualidade da experiência do cliente.

No que diz respeito ao Tempo Médio de Reparo, o indicador apresentou uma redução, passando de 0,41 dias em 2024 para 0,32 dias em 2025 — uma queda de aproximadamente 22%.

Já o Tempo Médio de Atendimento Inicial sofreu elevação, passando de 2,96 dias para 3,70 dias, o que representa um aumento de aproximadamente 25,0%. Esse crescimento sinaliza possíveis gargalos nas etapas iniciais de recepção e diagnóstico. Técnicos como F. P. S., que apresentava média de 4,96 dias no início de 2024, chegaram a 6,45 dias no mesmo período de 2025, indicando uma sobrecarga de atividades ou ausência de automação nos processos iniciais.

A Taxa de Retrabalho passou de 8,83% para 10,03%, configurando um alerta importante. Esse crescimento representa uma piora na qualidade técnica dos reparos, sobretudo quando observamos a taxa por equipamento. O destaque negativo fica para o Dreamcast, que em 2025 registrou uma taxa de retrabalho de 50%, seguido pelo Xbox 1 (12,82%) e PlayStation 3 (12,62%). A reincidência de falhas nesses modelos reforça a necessidade de revisar os procedimentos técnicos específicos para tais consoles, incluindo eventuais ações de capacitação ou revisão de protocolos de testes.

Por outro lado, ainda que alguns indicadores de tempo e qualidade tenham se deteriorado no comparativo entre os primeiros meses dos dois anos, é importante ressaltar que os dados não apontam para um descontrole do processo, mas sim para uma tendência de crescimento na demanda e na complexidade dos serviços. Diante disso, a empresa deve agir de forma preventiva, antecipando melhorias na distribuição de tarefas, na priorização de atendimentos e na capacitação contínua da equipe técnica.

**Figura 11 – Interface da página Produção com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024.**  

![Figura 11 - Interface da página Produção com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2024](/img/figura-11-producao-jan-abr-2024.png)

**Figura 12 – Interface da página Produção com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025.**  

![Figura 12 - Interface da página Produção com filtro aplicado para os meses de janeiro, fevereiro, março e abril de 2025](/img/figura-12-producao-jan-abr-2025.png)

A análise dos indicadores da aba Produção revela diferenças importantes no desempenho operacional da empresa entre os quatro primeiros meses dos anos de 2024 e 2025.

O Tempo Médio de Orçamento (TMO) aumentou de 3,91 dias em 2024 para 4,11 dias em 2025, o que representa um acréscimo de aproximadamente 5,1%. Por outro lado, o Tempo Médio de Diagnóstico reduziu-se de 1,00 dia para 0,54 dia no mesmo intervalo.

A Taxa de Aprovação de Orçamentos permaneceu em 100% nos dois períodos, enquanto a Taxa de Conversão de Orçamento apresentou leve queda, passando de 77,30% para 74,63%. Esse resultado indica estabilidade nos critérios de aprovação e comunicação com os clientes, ainda que a taxa de conversão tenha sido afetada, possivelmente, por fatores externos como custo final ou decisões do cliente.

No detalhamento por equipamento, observa-se que o tempo médio de orçamento para o PlayStation 2 caiu de 10,30 dias nos primeiros meses de 2024 para 4,51 dias no mesmo período de 2025. Já o tempo médio de orçamento para o Xbox 360 passou de 4,34 dias para 5,80 dias. Essa elevação pode indicar aumento da complexidade técnica dos orçamentos emitidos, além de sugerir dificuldades operacionais associadas à escassez de peças, necessidade de avaliação mais detalhada ou maior volume de serviços sob garantia.

#### 3.5.3. Recomendações sugeridas com base nas análises

Com base nos indicadores operacionais analisados ao longo dos períodos avaliados, é possível propor um conjunto de recomendações voltadas à melhoria contínua dos processos internos da empresa. As sugestões a seguir visam mitigar os pontos críticos identificados, consolidar os avanços já alcançados e sustentar a evolução do desempenho organizacional.

##### 3.5.3.1. Reforço na etapa de atendimento inicial e triagem técnica

O aumento no Tempo Médio de Atendimento Inicial nos primeiros meses de 2025, especialmente em comparação com o mesmo período de 2024, evidencia a necessidade de revisão dos fluxos de recepção, triagem e diagnóstico preliminar dos equipamentos. Recomenda-se a implementação de melhorias nos processos de alocação de tarefas e triagem automatizada, bem como a redistribuição equilibrada das ordens de serviço entre os técnicos, de forma a reduzir sobrecargas e evitar gargalos operacionais.

##### 3.5.3.2. Análise técnica aprofundada em modelos com alta taxa de retrabalho

A elevação da Taxa de Retrabalho, com destaque para equipamentos como Dreamcast, Xbox 1 e PlayStation 3, sugere fragilidades nos protocolos técnicos associados a esses modelos. Recomenda-se a revisão dos procedimentos padrão de reparo, a padronização de testes de qualidade e a realização de treinamentos específicos para os técnicos que atuam com maior frequência nesses equipamentos.

##### 3.5.3.3. Monitoramento de serviços com tempos de execução atípicos

Casos pontuais de serviços com tempos de execução extremamente elevados, como a “Recuperação da Placa de Vídeo do PlayStation 2”, impactam de forma significativa os indicadores médios e podem distorcer a percepção de desempenho. É recomendável estabelecer mecanismos de controle para identificar e tratar essas ocorrências de forma diferenciada, considerando sua natureza excepcional, a fim de preservar a fidelidade dos indicadores globais.

##### 3.5.3.4. Otimização dos prazos de orçamento

A ligeira elevação no Tempo Médio de Orçamento em 2025, observada especialmente no caso de alguns modelos como o Xbox 360 e Playstation Portátil, sugere a necessidade de revisão dos processos de elaboração e comunicação dos orçamentos. Recomenda-se avaliar a viabilidade de automatização parcial desse processo e a padronização dos critérios técnicos utilizados para compor os orçamentos, de modo a garantir agilidade e uniformidade.

##### 3.5.3.5. Acompanhamento contínuo da Taxa de Conversão de Orçamentos

Embora a Taxa de Aprovação tenha permanecido em 100%, a Taxa de Conversão apresentou uma tendência de queda entre os períodos avaliados. Recomenda-se o acompanhamento sistemático desse indicador, com a coleta de feedbacks dos clientes que optam por não autorizar os serviços, a fim de identificar possíveis fatores impeditivos como custo, prazo ou escopo técnico, e propor ajustes nas abordagens comerciais ou nos modelos de precificação.

##### 3.5.3.6. Fortalecimento da gestão da demanda e previsão de capacidade

A oscilação de alguns indicadores de desempenho, associada à ampliação da complexidade e do volume de serviços, aponta para a importância de aprimorar os mecanismos de previsão de demanda. Sugere-se a adoção de ferramentas de análise preditiva e a integração entre áreas técnicas e administrativas, com vistas à melhor alocação de recursos e ao dimensionamento adequado da força de trabalho.

### 3.6. Viabilidade técnica e financeira da estrutura desenvolvida

Nesta seção são apresentados os recursos tecnológicos utilizados na solução proposta, acompanhados de uma análise técnica e financeira que demonstra a viabilidade de sua adoção pela empresa.

#### 3.6.1. Estrutura tecnológica adotada

A arquitetura proposta para o sistema de Business Intelligence contempla três componentes principais:

- **Armazenamento de dados**: Banco de dados relacional MySQL Flexível (Azure).
- **Transformação de dados**: Ferramenta de transformação dbt Core (versão CLI).
- **Visualização de dados**: Power BI Desktop para criação de dashboards locais.

Essa estrutura foi escolhida por sua compatibilidade com a nuvem, escalabilidade progressiva e uso gratuito de ferramentas open-source. Além disso, o volume atual de dados da empresa é relativamente pequeno, com aproximadamente 800 MB de dados, o que permite iniciar a operação com uma configuração leve e de baixo custo.

#### 3.6.2. Justificativa técnica das escolhas

| Componente         | Justificativa técnica                                                                                                                                                 |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| MySQL Flexível (Azure) | Suporte à escalabilidade, backup automático, alta disponibilidade e integração com ferramentas nativas da Microsoft. A capacidade inicial é suficiente para hospedar os 800MB de dados atuais, com margem para expansão futura. |
| dbt Core           | Ferramenta open-source de transformação de dados com versionamento de modelos e modularidade. Pode ser executada localmente, sem custos adicionais.                  |
| Power BI Desktop   | Solução amplamente adotada para visualização de dados, com alto poder de criação de dashboards e sem custos iniciais de licenciamento. Ideal para análise local de dados. |

#### 3.6.3. Estimativa de custo mensal

| Categoria      | Recurso/Serviço                                                                                                                                                       | Custo estimado mensal |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|
| Banco de dados | Servidor MySQL flexível implantação, Camada com capacidade de intermitência, 1 B1MS (1 vCores) x 730 Horas, 1 vCore (B1MS), 5GB de armazenamento, ZRS, sem E/S paga     | R$191,98              |
| Transformação  | dbt Core CLI (open-source, executado localmente)                                                                                                                      | Gratuito              |
| Visualização   | Power BI Desktop                                                                                                                                                       | Gratuito              |
| **Total Estimado** |                                                                                                                                                                    | **R$191,98**          |

#### 3.6.4. Escalabilidade e cenários de custo

| Cenário de uso                        | Estimativa mensal       |
|--------------------------------------|--------------------------|
| Fase atual (dados pequenos, sem E/S) | R$191,98                 |
| Operação com 20GB e tráfego moderado | R$400,00 – R$600,00      |
| Crescimento contínuo (com backup e E/S) | R$800,00 – R$1.200,00 |

O monitoramento de custo e uso será feito por meio do Azure Cost Management, permitindo ajustes dinâmicos conforme o crescimento do volume de dados e acessos.

#### 3.6.5. Conclusão da viabilidade

A estrutura proposta é tecnicamente sólida, financeiramente viável e escalável. Com um custo mensal inicial inferior a R$200,00, a empresa poderá implantar um sistema de Business Intelligence completo, com visualizações interativas, controle de dados estruturado e possibilidade de crescimento conforme a demanda. Trata-se de uma solução estratégica e sustentável para suportar a evolução operacional da empresa.