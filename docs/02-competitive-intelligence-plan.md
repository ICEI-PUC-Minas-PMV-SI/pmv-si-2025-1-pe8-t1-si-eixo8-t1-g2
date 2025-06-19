# 2. Plano de Inteligência Competitiva

## 2.1. Identificação das necessidades de Inteligência Competitiva

### 2.1.1. Lista das principais decisões estratégicas da empresa

- **Previsibilidade dos prazos de manutenção**: A empresa precisa estimar com precisão o tempo necessário para realizar consertos em diferentes modelos de videogames e tipos de defeitos. Isso permite definir expectativas realistas para os clientes e melhorar a organização interna.
- **Eficiência operacional**: A redução de retrabalho e a otimização do fluxo de trabalho dentro da assistência técnica são essenciais para aumentar a produtividade da equipe e reduzir o tempo de espera dos clientes.
- **Gerenciamento da fila de atendimento**: A empresa precisa estabelecer critérios para priorizar os atendimentos, seja por tipo de serviço, equipamento, complexidade do reparo ou urgência do cliente. Um sistema eficiente de gerenciamento de fila pode reduzir atrasos e melhorar a satisfação do cliente.
- **Disponibilidade de peças**: A falta de componentes pode ser um grande fator de atraso nos reparos. A empresa precisa decidir quais peças devem ser mantidas em estoque e como melhorar a logística de reposição para evitar gargalos no atendimento.
- **Produtividade dos técnicos**: Monitorar o desempenho da equipe é crucial para identificar oportunidades de capacitação, redistribuir tarefas de forma eficiente e estabelecer metas realistas para a execução dos reparos.

### 2.1.2. Definição do Key Intelligence Topic

O *Key Intelligence Topic* (KIT) definido para este projeto refere-se à previsibilidade dos prazos de manutenção, com foco na otimização do tempo médio de manutenção e reparo de videogames. Esse tema é considerado crítico para a eficiência operacional da assistência técnica, impactando diretamente a satisfação do cliente, o planejamento de estoque e a produtividade da equipe técnica.

### 2.1.3. Formulação das Key Intelligence Questions

| **KIQ** | **Pergunta** | **Justificativa** |
|--------|--------------|-------------------|
| 01 | Qual é o tempo médio de execução dos diferentes tipos de serviço? | Mede a eficiência dos serviços prestados, permitindo identificar quais consertos são mais demorados e precisam ser otimizados. |
| 02 | Qual é o tempo médio de execução dos diferentes tipos de equipamento? | Consoles e acessórios possuem processos de manutenção distintos. Compreender essas variações ajuda na alocação de tempo e recursos. |
| 03 | Qual é o tempo médio de espera do cliente desde o recebimento até a entrega do videogame? | Longos tempos de espera podem indicar ineficiência no fluxo de trabalho. Reduzir esse tempo melhora a experiência do cliente. |
| 04 | Qual é a variação do tempo médio de reparo entre diferentes tipos de consoles e defeitos? | Alguns defeitos podem ser resolvidos rapidamente, enquanto outros exigem mais tempo. Essa análise ajuda na estimativa e planejamento. |
| 05 | Quais são os principais motivos de retrabalho nos reparos e como reduzi-los? | Se há falhas frequentes nos reparos, isso pode gerar desperdício de tempo e materiais. Identificar e corrigir esses problemas melhora a eficiência. |
| 06 | Como a distribuição das tarefas entre os técnicos impacta o tempo médio de reparo? | Técnicos sobrecarregados podem atrasar o serviço. Melhor equilibrar a carga de trabalho melhora a produtividade. |
| 07 | Qual deve ser o nível de estoque mínimo? | Manter um equilíbrio evita tanto a falta de peças quanto excessos que aumentam custos de armazenamento. |
| 08 | Qual deve ser o nível de estoque médio? | Manter um equilíbrio evita tanto a falta de peças quanto excessos que aumentam custos de armazenamento. |
| 09 | Qual deve ser o nível de estoque máximo? | Manter um equilíbrio evita tanto a falta de peças quanto excessos que aumentam custos de armazenamento. |
| 10 | Qual é o giro de estoque dos componentes mais utilizados? | Monitorar a frequência de reposição das peças ajuda a prever demandas e evitar desperdícios. |
| 11 | Qual é a cobertura de estoque para os itens essenciais? | Avaliar por quantos dias o estoque pode suprir a demanda evita interrupções no atendimento. |
| 12 | Qual é o tempo médio de reposição de peças pelos fornecedores? | Se o fornecedor demora para entregar peças, antecipar pedidos pode evitar atrasos nos reparos. |
| 13 | Qual é a taxa de ruptura de estoque na assistência técnica? | Mede quantas vezes uma peça essencial esteve em falta, impactando diretamente os prazos de reparo. |
| 14 | Qual é a taxa de obsolescência do estoque? | Peças que não são mais utilizadas representam perdas financeiras. Reduzir esse índice melhora a gestão do capital. |
| 15 | Qual é o tempo médio de permanência das peças no estoque antes de serem utilizadas? | Peças que ficam armazenadas por muito tempo podem representar um desperdício de espaço e capital. |
| 16 | Qual é o Tempo Médio de Atendimento Inicial (TMAI)? | Reduzir o tempo de registro e testes iniciais agiliza o processo sem comprometer o diagnóstico. |
| 17 | Qual é o Tempo Médio de Orçamento (TMO)? | Um orçamento rápido aumenta a taxa de conversão de clientes que aprovam o serviço. |
| 18 | Qual é a Taxa de Aprovação de Orçamentos (TAO)? | Uma taxa baixa pode indicar falhas na comunicação ou preços desalinhados ao mercado. |
| 19 | Qual é o Tempo Médio de Reparação (TMR)? | Reduzir o tempo de conserto aumenta a capacidade de atendimento da assistência técnica. |
| 20 | Qual é a Taxa de Retrabalho (TR)? | Se os reparos falham e precisam ser refeitos, há desperdício de tempo e recursos. |
| 21 | Qual é a Taxa de Conversão de Orçamentos por Técnico (TCOT)? | Se um técnico tem baixa taxa de conversão, pode precisar de treinamento para justificar melhor os serviços ao cliente. |
| 22 | Quantos Reparos cada Técnico conclui por período (NRCT)? | Mede a produtividade dos técnicos e ajuda a equilibrar a carga de trabalho. |
| 23 | Qual é o Tempo Médio de Diagnóstico por Técnico (TMDT)? | Diagnósticos demorados podem indicar necessidade de treinamento ou ferramentas mais eficientes. |
| 24 | Qual é a Taxa de Retrabalho por Técnico (TRT)? | Técnicos que apresentam muitas falhas precisam de ajustes em suas metodologias. |
| 25 | Qual é o Tempo Médio de Espera do Cliente (TMEC)? | Reduzir filas e tempos de espera melhora a experiência do cliente. |

### 2.1.4. Justificativa da relevância do KIT e das KIQs

A redução do tempo médio de manutenção é um diferencial competitivo no setor de assistência técnica. Um sistema de BI pode analisar padrões nos prazos de execução, identificar gargalos e otimizar processos, resultando em mais agilidade e satisfação do cliente. Além disso, pode ajudar a melhorar o planejamento de estoque e a produtividade da equipe técnica.

### 2.1.5. Fontes de dados identificadas para obtenção dessas informações

Os dados serão obtidos através do sistema ERP desenvolvido exclusivamente para a empresa. O sistema utiliza um banco de dados relacional MySQL, reconhecido por sua robustez e escalabilidade no armazenamento e gerenciamento de dados transacionais. O banco é gerenciado através da ferramenta Navicat 8, que oferece recursos avançados para administração, modelagem e otimização das consultas SQL.

### 2.1.6. Avaliação da disponibilidade e confiabilidade das fontes de dados

- **Disponibilidade dos dados**: Os dados do sistema podem ser importados através de arquivo `.csv` diretamente do Navicat ou poderá ser implementada uma API para importação direta do banco de dados.
- **Confiabilidade dos dados**: A integridade dos dados é assegurada por meio de restrições de integridade referencial, como chaves primárias e estrangeiras, garantindo consistência nas operações. O uso do Navicat 8 facilita a auditoria e análise da estrutura do banco, permitindo identificar possíveis falhas e melhorias no modelo de dados.

A avaliação da disponibilidade e confiabilidade das fontes de dados é adequada, pois garante que os dados necessários para a tomada de decisão estratégica estejam acessíveis e confiáveis. Reduz riscos operacionais ao assegurar que o banco de dados esteja estruturado para suportar operações comerciais sem falhas. Possibilita a integração com outras ferramentas de análise de dados, permitindo insights estratégicos baseados em informações consistentes e seguras.

## 2.2. Identificação das necessidades de informação

A seguir, são apresentados os principais KIQs definidos para o projeto:

| **KIQ** | **Pergunta** | **Métrica / Medição** | **Classificação** | **Fontes de Dados** | **Agrupamentos** | **Filtros** | **Visualização** | **Disponibilidade** | **Confiabilidade** |
|--------|--------------|------------------------|-------------------|---------------------|------------------|--------------|------------------|---------------------|---------------------|
| 01 | Qual é o tempo médio de execução dos diferentes tipos de serviço? | `AVERAGE(fct_ordens_servico[tempo_total_execucao_dias])` | Operações | fct_ordem_servico | tipo_servico | statusitem = "Concluído" | Gráfico de barras horizontal | Alta | Alta |
| 02 | Qual é o tempo médio de execução dos diferentes tipos de equipamento? | `SUM(data_fim_reparo - data_inicio_reparo) / COUNT(equipamentos)` | Operações | os, itensOS | Equipamento | statusitem = "Concluído" | Gráfico de barras empilhadas | Alta | Alta |
| 03 | Qual é o tempo médio de espera do cliente desde o recebimento até a entrega do videogame? | `AVG(data_entrega - data_recebimento)` | Operações | os, itensOS | Tipo de serviço, técnico ou equipamento | statusos = "Entregue" | Card | Alta | Alta |
| 04 | Qual é a variação do tempo médio de reparo entre diferentes tipos de consoles e defeitos? | `AVG(data_fim_reparo - data_inicio_reparo)` | Operações | os, itensOS | Equipamento, modelo e serviço | Status de conclusão e data de execução | Mapa de calor | Alta | Alta |
| 05 | Quais são os principais motivos de retrabalho nos reparos e como reduzi-los? | `(Qtd_retrabalhos / Qtd_reparos_concluídos) * 100` | Operações | os, itensOS | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 06 | Como a distribuição das tarefas entre os técnicos impacta o tempo médio de reparo? | `Total de OS atribuídas × tempo médio de reparo` | Operações | os, itensOS | Técnicos | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 07 | Qual deve ser o nível de estoque mínimo? | `CMD × dias de cobertura crítica` | Operações | os, itensOS, consumoitensos | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 08 | Qual deve ser o nível de estoque médio? | `CMD = total de peças utilizadas / número de dias analisados` | Operações | os, itensOS, consumoitensos | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 09 | Qual deve ser o nível de estoque máximo? | `CMD × lead time em dias` | Operações | os, itensOS, consumoitensos, oc, itensoc, ps | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 10 | Qual é o giro de estoque dos componentes mais utilizados? | `Consumo anual / Estoque médio` | Operações | consumoitensos, ps | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 11 | Qual é a cobertura de estoque para os itens essenciais? | `Estoque atual / Consumo médio diário (CMD)` | Operações | os, itensOS, consumoitensos, ps | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 12 | Qual é o tempo médio de reposição de peças pelos fornecedores? | `AVG(data_entrega_fornecedor - data_pedido)` | Operações | oc, itensoc | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 13 | Qual é a taxa de ruptura de estoque na assistência técnica? | `(OS com falta de peças / OS com requisição de peças) × 100` | Operações | os, itensOS, consumoitensos, ps | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 14 | Qual é a taxa de obsolescência do estoque? | `(Peças >365 dias sem uso / Estoque total) × 100` | Operações | os, itensOS, consumoitensos, ps | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 15 | Qual é o tempo médio de permanência das peças no estoque antes de serem utilizadas? | `AVG(data uso da peça - data entrada no estoque)` | Operações | os, itensOS, consumoitensos, oc, itensoc, ps | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 16 | Qual é o Tempo Médio de Atendimento Inicial (TMAI)? | `AVG(data_início_diagnóstico - data_abertura_os)` | Operações | os, itensOS | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 17 | Qual é o Tempo Médio de Orçamento (TMO)? | `AVG(data_abertura_os - data_início_diagnóstico)` | Operações | os, itensOS | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 18 | Qual é a Taxa de Aprovação de Orçamentos (TAO)? | `(count(data_autorizacao) / count(data_fim_orcamento)) × 100` | Operações | os, itensOS | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 19 | Qual é o Tempo Médio de Reparação (TMR)? | `AVG(data_fim_reparo - data_inicio_reparo)` | Operações | os, itensOS | Tipo de serviço, técnico ou equipamento | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 20 | Qual é a Taxa de Conversão de Orçamentos por Técnico (TCOT)? | `(count(data_autorizacao IS NOT NULL) / count(data_fim_orcamento)) × 100` | Operações | os, itensOS | Técnico | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 21 | Quantos Reparos cada Técnico conclui por período (NRCT)? | `COUNT(data_fim_reparo)` | Operações | os, itensOS | Data | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 22 | Qual é o Tempo Médio de Diagnóstico por Técnico (TMDT)? | `AVG(tempo_orcamento_dias)` | Operações | os, itensOS | Técnico | Status de conclusão e data de execução | Gráfico de barras | Alta | Alta |
| 23 | Qual é a Taxa de Retrabalho por Técnico (TRT)? | `(Qtd retrabalhos (OS tipo garantia) / Reparos concluídos) × 100` | Operações | os, itensOS | Técnico | idtecnicoconsertou | Gráfico de barras horizontal | Alta | Alta |
| 24 | Qual é a Taxa de Retrabalho por Técnico (TRT)? | `(Qtd retrabalhos (OS tipo garantia) / Reparos concluídos) × 100` | Operações | os, itensOS | Técnico | idtecnicoconsertou | Gráfico de barras horizontal | Alta | Alta |
| 25 | Qual é o Tempo Médio de Espera do Cliente (TMEC)? | `AVG(data_entrega - data_recebimento)` | Operações | os, itensOS | Tipo de serviço, técnico ou equipamento | statusos = "Entregue" | Gráfico de barras | Alta | Alta |

## 2.3. Planejamento da coleta e armazenamento de dados

Este tópico tem como objetivo estruturar um plano eficiente para a coleta, organização e armazenamento das informações que subsidiarão a futura solução de Business Intelligence (BI) da empresa.

### 2.3.1. Identificação das fontes de dados

A principal fonte de dados para o sistema de Business Intelligence será o sistema ERP proprietário da empresa, desenvolvido em C# e com banco de dados MySQL, gerenciado por meio da ferramenta Navicat 8.

A arquitetura do banco de dados é composta por 27 tabelas inter-relacionadas, distribuídas nos seguintes domínios:

- **Domínio operacional**: Tabelas que registram transações e eventos relacionados às atividades centrais da empresa. Incluem:
  - `os`: ordens de serviço e atendimentos técnicos
  - `itensos`: itens associados à OS, incluindo diagnósticos, soluções e técnicos responsáveis
  - `venda` e `itensvenda`: registros de vendas realizadas e produtos comercializados
  - `ps`: catálogo de produtos e serviços
  - `oc` e `itemoc`: ordens de compra e itens adquiridos
  - `caixa`: movimentações financeiras diárias

- **Domínio cadastral**: Tabelas que armazenam dados de referência relativamente estáveis, utilizados em diversos processos operacionais:
  - `pessoa`: cadastro unificado de clientes, funcionários e fornecedores
  - `aparelho`, `marca`, `modelo`: informações sobre os dispositivos atendidos
  - `centrocusto`, `tipocusto`, `tipopessoa`: classificações e categorias auxiliares
  - `registroponto`: controle de jornada de trabalho dos funcionários

- **Domínio financeiro**:
  - `titulo`: controle de contas a pagar e a receber

- **Domínio de governança e comunicação**:
  - `tblpermissao`, `tblpermissaopag`, `permissao`: controle de acesso por usuário
  - `mural`, `texto`: informações e avisos internos da empresa

### 2.3.2. Métodos de coleta de dados

Diante das limitações do sistema ERP atual, optou-se pela coleta de dados via exportação manual de arquivos no formato `.csv`, diretamente pela ferramenta Navicat 8. Essa abordagem permite viabilidade técnica no curto prazo e oferece flexibilidade para tratamento e transformação dos dados em etapas posteriores.

### 2.3.3. Plano de coleta estruturado

**Cronograma de coleta:**

- **Fase de coleta inicial**: Será realizada uma extração completa do histórico de dados, com o objetivo de construir uma base de referência inicial para análises retroativas.
- **Fase de atualização incremental**: Estão previstos ciclos mensais de atualização dos dados, com extração apenas dos registros modificados ou adicionados desde a última coleta.

**Responsabilidades:**

- **Responsável pela extração**: Executa a coleta conforme o cronograma, verifica a integridade dos arquivos exportados e realiza os registros necessários.
- **Responsável pela validação**: Realiza auditorias periódicas na qualidade dos dados coletados, detectando e corrigindo eventuais inconsistências.

### 2.3.4. Estratégia de armazenamento de dados

A estratégia de armazenamento será baseada na arquitetura em camadas (*medallion architecture*), amplamente adotada em projetos de Business Intelligence. Os dados serão processados em quatro camadas distintas, cada uma com objetivos específicos:

| **Camada**         | **Objetivo**                                                                 | **Ferramenta**                   |
|--------------------|------------------------------------------------------------------------------|----------------------------------|
| Bruta (*raw*)       | Preservar os dados originais sem modificações para rastreabilidade           | Azure Data Lake Storage (ADLS)   |
| Inicial (*staging*) | Padronização estrutural (tipos de dados, nomenclatura, limpeza básica)       | dbt (Data Build Tool) e SQL      |
| Intermediária       | Aplicação de regras de negócio e pré-modelagem dimensional                   | dbt (Data Build Tool) e SQL      |
| Analítica (*mart*)  | Modelagem dimensional final (*Star Schema*) para consumo no Power BI        | Microsoft Power BI               |

### 2.3.5. Métodos de organização e classificação dos dados

Os dados serão organizados com base na modelagem dimensional, adotando a estrutura estrela (*star schema*). Nesse modelo, os dados são divididos em:

- **Tabelas fato**: Armazenam os eventos transacionais do negócio (como ordens de serviço, vendas e lançamentos financeiros), com atributos quantitativos e relacionamentos com múltiplas dimensões.
- **Tabelas dimensão**: Armazenam dados descritivos e de referência (como clientes, produtos, técnicos e tempo), permitindo análises detalhadas sob diferentes perspectivas.

Essa abordagem é recomendada para projetos de Business Intelligence por sua simplicidade, facilidade de leitura e desempenho nas consultas analíticas, conforme defendem Kimball e Ross (2013).

## 2.4. Análise de dados e registro de informações

### 2.4.1.1. Escolha das ferramentas de análise

- **Power BI**: Será a ferramenta principal para visualização de dados e criação de dashboards interativos. Permite análise em tempo real de KPIs, geração de gráficos e relatórios interativos, facilitando a tomada de decisão estratégica.

- **dbt (Data Build Tool)**: Será a principal ferramenta para tratamento e transformação dos dados. Com o dbt, será possível criar pipelines que limpam, estruturam e transformam dados de maneira eficiente, gerando tabelas e modelos otimizados para análise. O dbt também permite aplicação de regras de negócio, modelagem dimensional, versionamento e documentação das transformações, contribuindo para a governança e confiabilidade dos dados.

### 2.4.1.2. Estratégias de análise

- **Análise de tendências**: Usando o Power BI, será possível analisar padrões ao longo do tempo (como volume de reparos, tipos de defeitos mais frequentes e tempo médio de reparo), ajudando a prever mudanças no comportamento e permitindo que a empresa se antecipe a gargalos.

- **Segmentação de clientes**: O dbt transformará e organizará os dados de clientes, criando agrupamentos com base em histórico de serviços, tipo de videogame e tempo de resposta. O Power BI permitirá a visualização desses segmentos e a geração de insights sobre preferências de compra e necessidades de manutenção.

- **Modelagem preditiva**: Utilizando dados tratados pelo dbt, o Power BI permitirá realizar análises preditivas para estimar tempo de reparo por tipo de defeito e prever demanda por peças. Isso ajudará a optimizar processos internos e reduzir tempos de espera.

- **Análise de correlação**: O Power BI facilitará a identificação de relações entre variáveis, como tempo de reparo e tipo de defeito, permitindo ajustes para redução de falhas e melhoria da produtividade.

- **Análise de KPI e métricas operacionais**: KPIs essenciais como Tempo Médio de Reparação, Taxa de Retrabalho e Taxa de Conversão de Orçamentos serão visualizados de forma clara no Power BI, permitindo acompanhamento eficaz do desempenho pela gestão.

### 2.4.1.3. Geração de insights

- **Tempo de manutenção e reparo**: O Power BI identificará quais reparos são mais demorados e os fatores que impactam esse tempo (como tipo de defeito ou modelo de videogame). O dbt estruturará os dados para cálculo de métricas como "tempo médio de reparo" por tipo de defeito.

- **Produtividade da equipe técnica**: O dbt processará os dados dos técnicos para calcular indicadores como número de reparos por período e taxa de retrabalho. O Power BI visualizará o desempenho individual e identificará necessidades de capacitação.

- **Disponibilidade de peças**: Com dados tratados no dbt, será possível correlacionar a falta de peças com atrasos. O Power BI exibirá informações sobre estoque e taxas de ruptura, contribuindo para um melhor gerenciamento.

- **Identificação de gargalos**: O Power BI destacará gargalos no processo de manutenção, como atrasos por falta de peças ou falhas no diagnóstico inicial. Com esses dados, a equipe poderá tomar ações corretivas e otimizar os fluxos operacionais.

## 2.5. Disseminação e utilização das informações

A disseminação eficaz das informações é essencial para que os insights gerados pelo processo de Inteligência Competitiva influenciem as decisões da empresa de forma estratégica. Para esse fim, foram selecionadas as ferramentas Power BI e PowerPoint, que oferecem formatos versáteis de apresentação, como dashboards, relatórios interativos e apresentações executivas, adaptando-se às diferentes necessidades dos tomadores de decisão.

**Power BI**: O Power BI será utilizado como ferramenta central para a criação de dashboards e relatórios interativos. Sua conexão será estabelecida com a camada analítica do Data Lake, permitindo que os dados previamente estruturados e tratados possam ser facilmente visualizados pelos gestores. Como o processo de atualização não será automatizado, a alimentação dos dashboards ocorrerá conforme ciclos previamente definidos, seguindo o cronograma estabelecido para a extração manual dos dados em formato `.csv` e sua posterior ingestão na plataforma Azure.

Para assegurar que as informações produzidas sejam efetivamente incorporadas ao processo decisório da empresa, estão previstas as seguintes ações:

- **Validação e feedback dos usuários internos**: Realização de testes e sessões de validação com os tomadores de decisão, com o objetivo de ajustar os dashboards e relatórios às necessidades reais da organização.

- **Rotina de atualização e monitoramento**: Definição de ciclos regulares de atualização dos relatórios e dashboards, de acordo com o planejamento técnico da coleta e ingestão dos dados. Essa rotina permitirá o monitoramento contínuo da qualidade das informações, possibilitando ajustes e melhorias ao longo do tempo.

Para garantir que os dados estejam disponíveis no momento certo para subsidiar decisões estratégicas, foram estabelecidas as seguintes práticas:

- **Atualização programada**: Como a atualização será realizada por ciclos de extração manual, será definido um cronograma fixo para garantir previsibilidade no acesso aos dados atualizados, alinhando as entregas às principais rotinas de gestão da empresa.

- **Notificações**: A cada nova atualização dos dashboards, serão enviadas comunicações por e-mail, informando a disponibilização das informações, de forma a garantir que os tomadores de decisão tenham acesso aos dados no momento oportuno.

- **Agenda de reuniões estratégicas**: Serão definidas agendas periódicas de reuniões com base nas informações mais recentes disponibilizadas, possibilitando que os insights gerados contribuam diretamente para os processos de revisão de desempenho, planejamento e definição de metas.

Com essas medidas, garante-se que os insights produzidos pelo sistema de Business Intelligence (BI) sejam acessíveis, compreensíveis e estrategicamente relevantes, contribuindo para a melhoria contínua dos processos organizacionais e para a consolidação de uma cultura empresarial orientada por dados.

## 2.6. Avaliação do processo de Inteligência Competitiva

### 2.6.1. Revisão da eficiência do processo de coleta e análise

O processo de construção do Plano de Inteligência Competitiva demonstrou coerência entre as etapas propostas e os objetivos estratégicos da empresa. A identificação das necessidades de decisão, seguida da definição do KIT e formulação das KIQs, possibilitou um mapeamento preciso dos principais pontos críticos da operação.

A estruturação das perguntas estratégicas foi acompanhada por um levantamento detalhado dos dados necessários, suas fontes, formas de visualização e avaliação de disponibilidade. A escolha da extração manual dos dados via arquivos `.csv` diretamente do ERP mostrou-se viável neste primeiro momento, possibilitando acesso aos dados essenciais mesmo na ausência de automações.

A adoção de uma arquitetura de armazenamento em camadas (*medallion architecture*) e a proposta de modelagem dimensional (*star schema*) reforçaram a eficiência do processo, preparando o ambiente para a análise estruturada e escalável dos dados.

### 2.6.2. Feedback dos usuários finais

A validação do Plano de Inteligência Competitiva será realizada pelo proprietário da empresa, que já analisou a proposta e manifestou aprovação quanto à sua aplicabilidade e relevância para o contexto da organização. De acordo com sua avaliação preliminar, o plano atende plenamente às expectativas, oferecendo um mapeamento claro e bem estruturado das informações críticas para a gestão da assistência técnica.

O proprietário destacou que os indicadores propostos são altamente compatíveis com a realidade operacional da organização, apresentando potencial para gerar insights relevantes tanto para decisões operacionais quanto para o planejamento estratégico. A clareza das perguntas de inteligência e sua adequação às rotinas internas foram apontadas como diferenciais positivos da proposta.

Além disso, o gestor demonstrou entusiasmo com a futura implementação dos dashboards no Power BI, ressaltando a importância de manter a equipe alinhada a uma cultura orientada por dados, como fator essencial para o sucesso do projeto.

Entre os principais pontos positivos apontados estão:

- Visibilidade sobre a produtividade individual e coletiva da equipe técnica;
- Compreensão mais clara sobre gargalos no processo de manutenção;
- Possibilidade de planejamento mais assertivo da reposição de peças e insumos.

### 2.6.3. Potenciais desafios

Com base na análise do contexto e características técnicas do projeto, é possível antecipar alguns desafios que poderão surgir durante a implementação do Plano de Inteligência Competitiva:

- **Integração limitada do sistema de ERP**: A ausência de APIs ou conectores nativos poderá dificultar a automatização da extração de dados, tornando o processo mais dependente de rotinas manuais por meio de arquivos `.csv`. Tal limitação poderá impactar negativamente a escalabilidade e a confiabilidade do fluxo de dados.

- **Qualidade e padronização dos dados**: Existe o risco de inconsistências nos dados históricos, presença de campos preenchidos de forma livre e ausência de categorização padronizada, fatores que podem dificultar o tratamento e a modelagem das informações na etapa de transformação.

- **Falta de documentação da estrutura do banco de dados**: A inexistência de um dicionário de dados formal poderá comprometer a compreensão da base por parte de novos integrantes da equipe de dados, além de dificultar futuras manutenções e evoluções da arquitetura da informação.

### 2.6.4. Melhoria contínua

Com base na análise crítica do planejamento proposto, são apresentadas recomendações para o aprimoramento contínuo da futura implementação do processo de Inteligência Competitiva:

- **Estabelecimento de um plano de governança de dados**: Definir padrões para nomenclatura de campos, validação de registros, periodicidade de atualização e atribuição de responsabilidades, com o objetivo de garantir a integridade e a confiabilidade das informações ao longo do tempo.

- **Automatização progressiva do processo de coleta**: Avaliar a viabilidade de implementação futura de mecanismos de automação para a extração e ingestão dos dados, com o objetivo de reduzir a dependência de processos manuais e ampliar a frequência de atualização dos relatórios.

- **Documentação da estrutura do banco de dados**: Desenvolver um dicionário de dados contendo a descrição de tabelas, campos, relacionamentos e regras de negócio, promovendo maior transparência e facilitando a manutenção do modelo de dados.

- **Criação de rotinas de validação e atualização contínua**: Estabelecer pontos de controle periódicos para revisão da qualidade dos dados, atualização dos dashboards e ajustes nas análises conforme o uso prático e os feedbacks dos usuários.

- **Capacitação sobre indicadores e dashboards**: Promover treinamentos periódicos com os gestores e com a equipe técnica, com foco na interpretação dos indicadores, no uso adequado das visualizações e na aplicação prática dos insights gerados para a melhoria da operação.

## 2.7. Compliance de TI e Segurança da Informação

Este tópico tem como objetivo garantir que os processos de Inteligência Competitiva (IC) estejam em conformidade com as legislações vigentes e as melhores práticas em segurança da informação. A conformidade com normas como a Lei Geral de Proteção de Dados (LGPD), bem como a adoção de políticas estruturadas de segurança, é essencial para assegurar a integridade, a confidencialidade e a disponibilidade dos dados tratados.

### 2.7.1. Mapeamento de normas e regulamentações aplicáveis

O uso de dados pessoais e sensíveis no contexto empresarial exige atenção aos seguintes marcos regulatórios:

**Lei Geral de Proteção de Dados (LGPD)**

A LGPD (Lei nº 13.709/2018) regula o tratamento de dados pessoais no Brasil e estabelece princípios como:

- Finalidade e transparência na coleta e tratamento de dados;
- Consentimento do titular dos dados;
- Segurança e prevenção contra vazamento de informações;
- Direitos do titular, incluindo acesso, correção e exclusão de dados;
- Responsabilização e prestação de contas pelas empresas que tratam dados pessoais.

A LGPD impacta diretamente a operação da empresa, uma vez que seus sistemas armazenam e processam dados pessoais de clientes, fornecedores e funcionários. Assim, medidas de compliance precisam ser implementadas para garantir a conformidade com essa legislação.

### 2.7.2. Políticas de proteção de dados e segurança da informação

Para minimizar riscos, a empresa deve adotar estratégias como anonimização e pseudonimização dos dados sensíveis, garantindo que as informações pessoais não possam ser vinculadas diretamente a indivíduos. Essa abordagem auxilia a organização a ficar em compliance com a LGPD.

O armazenamento de dados deve ser restrito ao essencial, utilizando criptografia avançada para que somente usuários autorizados tenham acesso. Além disso, procedimentos de exclusão segura devem ser implementados para eliminar permanentemente informações que não são mais necessárias.

O controle de acessos deve ser rigoroso, empregando autenticação de dois fatores (2FA) e concessão de permissões de acordo com a função do usuário. O registro detalhado de acessos e modificações a partir dos logs nos sistemas deve ser mantido para auditorias futuras, e revisões periódicas das permissões devem garantir que funcionários desligados ou sem necessidade de acesso não possam manipular os dados. Estratégias para identificar e bloquear acessos não autorizados ou suspeitos também devem ser estabelecidas.

No que se refere à transferência e armazenamento de dados, é fundamental utilizar criptografia tanto em repouso quanto em trânsito, além de garantir conexões seguras (SSL/TLS) para a transmissão de informações sensíveis. Backups regulares devem ser realizados, juntamente com procedimentos de recuperação de desastres para assegurar a continuidade das operações. O monitoramento de tráfego deve ser constante para identificar atividades incomuns e possibilitar respostas rápidas a incidentes. Métodos de armazenamento descentralizado e replicação de dados devem ser considerados para aumentar a resiliência e reduzir os impactos de falhas técnicas.

## 2.7.3. Auditoria e conformidade

### 2.7.3. Auditoria e conformidade

Para manter a conformidade, a empresa deve realizar auditorias regulares, avaliando a segurança da informação, monitorando tentativas de acesso indevido e documentando vulnerabilidades e medidas corretivas adotadas. O uso de ferramentas especializadas em análise de vulnerabilidades auxilia na detecção de falhas antes que possam ser exploradas. Além disso, deve ser estabelecido um plano de resposta a incidentes para garantir ações ágeis e eficazes diante de eventuais violações de segurança.

A capacitação dos colaboradores desempenha um papel fundamental na segurança da informação. Treinamentos frequentes sobre boas práticas, gestão de senhas e atualizações de sistemas são essenciais. Simulações de ataques podem ser conduzidas para testar a conscientização da equipe e identificar pontos de melhoria. Campanhas internas também devem reforçar a importância da segurança de dados, e treinamentos específicos por nível hierárquico ajudarão na disseminação de responsabilidades dentro da organização.