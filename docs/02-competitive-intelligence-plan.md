# 2. PLANO DE INTELIGÊNCIA COMPETITIVA
   
## 2.1. Identificação das necessidades de Inteligência Competitiva

## 2.1.1. Lista das principais decisões estratégicas da empresa

- Previsibilidade dos prazos de manutenção: A empresa precisa estimar
com precisão o tempo necessário para realizar consertos em diferentes
modelos de videogames e tipos de defeitos. Isso permite definir expectativas
realistas para os clientes e melhorar a organização interna.
- Eficiência operacional: A redução de retrabalho e a otimização do fluxo de
trabalho dentro da assistência técnica são essenciais para aumentar a
produtividade da equipe e reduzir o tempo de espera dos clientes.
- Gerenciamento da fila de atendimento: A empresa precisa estabelecer
critérios para priorizar os atendimentos, seja por tipo de serviço, equipamento,
complexidade do reparo ou urgência do cliente. Um sistema eficiente de
gerenciamento de fila pode reduzir atrasos e melhorar a satisfação do cliente.
- Disponibilidade de peças: A falta de componentes pode ser um grande
fator de atraso nos reparos. A empresa precisa decidir quais peças devem ser
mantidas em estoque e como melhorar a logística de reposição para evitar
gargalos no atendimento.
- Produtividade dos técnicos: Monitorar o desempenho da equipe é crucial
para identificar oportunidades de capacitação, redistribuir tarefas de forma
eficiente e estabelecer metas realistas para a execução dos reparos.

## 2.1.2. Definição do Key Intelligence Topic

O Key Intelligence Topic (KIT) definido para este projeto refere-se à
previsibilidade dos prazos de manutenção, com foco na otimização do tempo médio
de manutenção e reparo de videogames. Esse tema é considerado crítico para a
eficiência operacional da assistência técnica, impactando diretamente a satisfação
do cliente, o planejamento de estoque e a produtividade da equipe técnica.

## 2.1.3. Formulação das Key Intelligence Questions

A formulação das Key Intelligence Questions (KIQs) visa orientar a coleta e
análise de dados de modo a transformar informações operacionais em insights
estratégicos. As perguntas a seguir foram elaboradas com base nos objetivos
definidos no KIT, buscando identificar pontos críticos da operação e subsidiar a
tomada de decisões:

|**KIQ**|**Pergunta**|**Justificativa**|
|------|------|------|
| 01 | Qual é o tempo médio de execução dos diferentes tipos de serviço? | Mede a eficiência dos serviços prestados, permitindo identificar quais consertos são mais demorados e precisam ser otimizados. |
| 02 | Qual é o tempo médio de execução dos diferentes tipos de equipamento? | Consoles e acessórios possuem processos de manutenção distintos. Compreender essas variações ajuda na alocação de tempo e recursos.
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
| 14 | Qual é a taxa de obsolescência do estoque? | Peças que não são mais utilizadas representam perdas financeiras. Reduzir esse índice melhora a gestão do capital.
| 15 | Qual é o tempo médio de permanência das peças no estoque antes de serem utilizadas? | Peças que ficam armazenadas por muito tempo podem representar um desperdício de espaço e capital. |
| 16 | Qual é o Tempo Médio de Atendimento Inicial (TMAI)? | Reduzir o tempo de registro e testes iniciais agiliza o processo sem comprometer o diagnóstico. |
| 17 | Qual é o Tempo Médio de Orçamento (TMO)? | Um orçamento rápido aumenta a taxa de conversão de clientes que aprovam o serviço. |
| 18 | Qual é a Taxa de Aprovação de Orçamentos (TAO)? | Uma taxa baixa pode indicar falhas na comunicação ou preços desalinhados ao mercado. |
| 19 | Qual é o Tempo Médio de Reparação (TMR)? | Reduzir o tempo de conserto aumenta a capacidade de atendimento da assistência técnica. |
| 20 | Qual é a Taxa de Retrabalho (TR)? | Se os reparos falham e precisam ser refeitos, há desperdício de tempo e recursos. |
| 21 | Qual é a Taxa de Conversão de Orçamentos por Técnico (TCOT)? | Se um técnico tem baixa taxa de conversão, pode precisar de treinamentopara justificar melhor os serviços ao cliente. |
| 22 | Quantos Reparos cada Técnico conclui por período (NRCT)? | Mede a produtividade dos técnicos e ajuda a equilibrar a carga de trabalho. |
| 23 | Qual é o Tempo Médio de Diagnóstico por Técnico (TMDT)? | Diagnósticos demorados podem indicar necessidade de treinamento ou ferramentas mais eficientes. |
| 24 | Qual é a Taxa de Retrabalho por Técnico (TRT)? | Técnicos que apresentam muitas falhas precisam de ajustes em suas metodologias. |
| 25 | Qual é o Tempo Médio de Espera do Cliente (TMEC)? | Reduzir filas e tempos de espera melhora a experiência do cliente. |

## 2.1.4 Justificativa da relevância do KIT e das KIQs
A redução do tempo médio de manutenção é um diferencial competitivo no
setor de assistência técnica. Um sistema de BI pode analisar padrões nos prazos de
execução, identificar gargalos e otimizar processos, resultando em mais agilidade e
satisfação do cliente. Além disso, pode ajudar a melhorar o planejamento de estoque
e a produtividade da equipe técnica.
## 2.1.5 Fontes de dados identificadas para obtenção dessas informações
Os dados serão obtidos através do sistema ERP desenvolvido exclusivamente
para a empresa. O sistema utiliza um banco de dados relacional MySQL,
reconhecido por sua robustez e escalabilidade no armazenamento e gerenciamento
de dados transacionais. O banco é gerenciado através da ferramenta Navicat 8, que
oferece recursos avançados para administração, modelagem e otimização das
consultas SQL.
## 2.1.6 Avaliação da disponibilidade e confiabilidade das fontes de dados
- Disponibilidade dos dados: Os dados do sistema podem ser importados
através de arquivo .csv diretamente do Navicat ou poderá ser implementado
API para importação direta do banco de dados.
- Confiabilidade dos dados: A integridade dos dados é assegurada por meio
de restrições de integridade referencial, como chaves primárias e
estrangeiras, garantindo consistência nas operações. O uso do Navicat 8
facilita a auditoria e análise da estrutura do banco, permitindo identificar
possíveis falhas e melhorias no modelo de dados.
A avaliação da disponibilidade e confiabilidade das fontes de dados é
adequada, pois garante que os dados necessários para a tomada de decisão
estratégica estejam acessíveis e confiáveis. Reduz riscos operacionais ao assegurar
que o banco de dados esteja estruturado para suportar operações comerciais sem
falhas. Possibilita a integração com outras ferramentas de análise de dados,
permitindo insights estratégicos baseados em informações consistentes e seguras.
## 2.2. Identificação das necessidades de informação

A seguir, são apresentados os principais KIQs definidos para o projeto:

### KIQ 01 – Qual é o tempo médio de execução dos diferentes tipos de serviço?

| Componente                  | Descrição                                                                                                                                       |
|----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `Tempo Médio de Execução = SUM(data_fim_reparo - data_inicio_reparo) / COUNT(serviços)`                                                        |
| Classificação da Informação| Operações                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                         |
| Agrupamentos               | Serviços                                                                                                                                        |
| Filtros                    | `statusitem = "Concluído"`                                                                                                                      |
| Visualização               | Gráfico de barras horizontal                                                                                                                    |
| Disponibilidade            | Alta – Os dados são armazenados no ERP da empresa e podem ser extraídos via `.csv` ou API. Estão disponíveis nas tabelas especificadas e acessíveis para construção de dashboards. |
| Confiabilidade             | Alta – O sistema ERP utiliza banco de dados MySQL com integridade referencial. Os dados são consistentes e auditáveis via Navicat, garantindo confiabilidade para análises. |


### KIQ 02 – Qual é o tempo médio de execução dos diferentes tipos de equipamento?

| Componente                  | Descrição                                                                                                                                    |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `Tempo Médio Execução = SUM(data_fim_reparo - data_inicio_reparo) / COUNT(equipamentos)`                                                    |
| Classificação da Informação| Operações                                                                                                                                    |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                      |
| Agrupamentos               | Equipamento                                                                                                                                  |
| Filtros                    | `statusitem = "Concluído"`                                                                                                                   |
| Visualização               | Gráfico de barras empilhadas                                                                                                                |
| Disponibilidade            | Alta                                                                                                                                        |
| Confiabilidade             | Alta                                                                                                                                        |


### KIQ 03 – Qual é o tempo médio de espera do cliente desde o recebimento até a entrega do videogame?

| Componente                  | Descrição                                                                                                                                    |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `TMEC = AVG(data_entrega - data_recebimento)`                                                                                                |
| Classificação da Informação| Operações                                                                                                                                    |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                      |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                      |
| Filtros                    | `statusos = "Entregue"`                                                                                                                      |
| Visualização               | Card                                                                                                                                         |
| Disponibilidade            | Alta                                                                                                                                        |
| Confiabilidade             | Alta                                                                                                                                        |


### KIQ 04 – Qual é a variação do tempo médio de reparo entre diferentes tipos de consoles e defeitos?

| Componente                  | Descrição                                                                                                                                    |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `TMR = AVG(data_fim_reparo - data_inicio_reparo)`                                                                                            |
| Classificação da Informação| Operações                                                                                                                                    |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                      |
| Agrupamentos               | Equipamento, modelo e serviço                                                                                                                |
| Filtros                    | Status de conclusão e data de execução                                                                                                       |
| Visualização               | Mapa de calor                                                                                                                                |
| Disponibilidade            | Alta                                                                                                                                        |
| Confiabilidade             | Alta                                                                                                                                        |


### KIQ 05 – Quais são os principais motivos de retrabalho nos reparos e como reduzi-los?

| Componente                  | Descrição                                                                                                                                    |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `Taxa de retrabalho = (Qtd_retrabalhos / Qtd_reparos_concluídos) * 100`                                                                     |
| Classificação da Informação| Operações                                                                                                                                    |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                      |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                      |
| Filtros                    | Status de conclusão e data de execução                                                                                                       |
| Visualização               | Gráfico de barras                                                                                                                            |
| Disponibilidade            | Alta                                                                                                                                        |
| Confiabilidade             | Alta                                                                                                                                        |



### KIQ 06 – Como a distribuição das tarefas entre os técnicos impacta o tempo médio de reparo?

| Componente                  | Descrição                                                                                                                                    |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `Total de OS atribuídas × tempo médio de reparo`                                                                                             |
| Classificação da Informação| Operações                                                                                                                                    |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                      |
| Agrupamentos               | Técnicos                                                                                                                                     |
| Filtros                    | Status de conclusão e data de execução                                                                                                       |
| Visualização               | Gráfico de barras                                                                                                                            |
| Disponibilidade            | Alta                                                                                                                                        |
| Confiabilidade             | Alta                                                                                                                                        |


### KIQ 07 – Qual deve ser o nível de estoque mínimo?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `Estoque mínimo = CMD × dias de cobertura crítica = (maior consumo diário / consumo médio diário)`                                                            |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`, `consumoitensos`                                                                                                                      |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 08 – Qual deve ser o nível de estoque médio?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `CMD = total de peças utilizadas / número de dias analisados`                                                                                                  |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`, `consumoitensos`                                                                                                                      |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 09 – Qual deve ser o nível de estoque máximo?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `Estoque máximo = CMD × lead time em dias = média(data_recebimento - data_pedido)`                                                                             |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`, `consumoitensos`, `oc`, `itensoc`, `ps`                                                                                                |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 10 – Qual é o giro de estoque dos componentes mais utilizados?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `Giro de estoque = Consumo anual / Estoque médio`                                                                                                               |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `consumoitensos`, `ps`                                                                                                                                  |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 11 – Qual é a cobertura de estoque para os itens essenciais?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `Cobertura de estoque = Estoque atual / Consumo médio diário (CMD)`                                                                                            |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`, `consumoitensos`, `ps`                                                                                                                 |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 12 – Qual é o tempo médio de reposição de peças pelos fornecedores?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `Tempo médio = AVG(data_entrega_fornecedor - data_pedido)`                                                                                                     |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `oc`, `itensoc`                                                                                                                                         |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 13 – Qual é a taxa de ruptura de estoque na assistência técnica?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `Taxa de ruptura (%) = (OS que requisitam peças em dias com estoque zerado / OS autorizadas que requisitam peças) × 100`                                     |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`, `consumoitensos`, `ps`                                                                                                                 |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 14 – Qual é a taxa de obsolescência do estoque?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `Taxa de obsolescência = (Qtd peças obsoletas (>365 dias sem uso) / Qtd total em estoque) × 100`                                                              |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`, `consumoitensos`, `ps`                                                                                                                 |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 15 – Qual é o tempo médio de permanência das peças no estoque antes de serem utilizadas?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `AVG(data uso da peça - data entrada no estoque)`                                                                                                              |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`, `consumoitensos`, `oc`, `itensoc`, `ps`                                                                                                |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 16 – Qual é o Tempo Médio de Atendimento Inicial (TMAI)?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `AVG(data início diagnóstico - data recebimento equipamento)`                                                                                                  |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                                         |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 17 – Qual é o Tempo Médio de Orçamento (TMO)?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `AVG(data envio orçamento - data início diagnóstico)`                                                                                                          |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                                         |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 18 – Qual é a Taxa de Aprovação de Orçamentos (TAO)?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `(Qtd aprovados / Qtd enviados) × 100`                                                                                                                          |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                                         |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 19 – Qual é o Tempo Médio de Reparação (TMR)?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `AVG(data_fim_reparo - data_inicio_reparo)`                                                                                                                    |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                                         |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 20 – Qual é a Taxa de Retrabalho (TR)?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `(Qtd retrabalhos / Qtd total de reparos) × 100`                                                                                                               |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                                         |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 21 – Qual é a Taxa de Conversão de Orçamentos por Técnico (TCOT)?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `(Orçamentos aprovados / Orçamentos enviados) × 100`                                                                                                           |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                                         |
| Agrupamentos               | Técnico                                                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 22 – Quantos Reparos cada Técnico conclui por período (NRCT)?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `COUNT(reparos_concluídos)`                                                                                                                                    |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                                         |
| Agrupamentos               | Data                                                                                                                                                           |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 23 – Qual é o Tempo Médio de Diagnóstico por Técnico (TMDT)?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `AVG(data conclusão diagnóstico - data início diagnóstico)`                                                                                                    |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                                         |
| Agrupamentos               | Técnico                                                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Gráfico de barras                                                                                                                                              |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 24 – Qual é a Taxa de Retrabalho por Técnico (TRT)?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `(Retrabalhos realizados (OS tipo garantia) / Reparos concluídos) × 100`                                                                                      |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                                         |
| Agrupamentos               | Técnico                                                                                                                                                        |
| Filtros                    | `idtecnicoconsertou`                                                                                                                                            |
| Visualização               | Gráfico de barras horizontal                                                                                                                                   |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


### KIQ 25 – Qual é o Tempo Médio de Espera do Cliente (TMEC)?

| Componente                  | Descrição                                                                                                                                                      |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica/Medição            | `AVG(data_entrega - data_recebimento)`                                                                                                                         |
| Classificação da Informação| Operações                                                                                                                                                       |
| Fontes de Dados            | Tabelas `os`, `itensOS`                                                                                                                                         |
| Agrupamentos               | Tipo de serviço, técnico ou equipamento                                                                                                                        |
| Filtros                    | Status de conclusão e data de execução                                                                                                                         |
| Visualização               | Card                                                                                                                                                           |
| Disponibilidade            | Alta                                                                                                                                                           |
| Confiabilidade             | Alta                                                                                                                                                           |


## 2.3. Planejamento da coleta e armazenamento de dados

Este tópico tem como objetivo estruturar um plano eficiente para a coleta,
organização e armazenamento das informações que subsidiarão a futura solução de
Business Intelligence (BI) da empresa Electronic Games BH.
## 2.3.1. Identificação das fontes de dados

A principal fonte de dados para o sistema de Business Intelligence será o
sistema ERP proprietário da Eletronic Games, desenvolvido em C# e com banco de
dados MySQL, gerenciado por meio da ferramenta Navicat 8. A arquitetura do banco
de dados é composta por 27 tabelas inter-relacionadas, distribuídas nos seguintes
domínios:

1. Domínio operacional: Tabelas que registram transações e eventos
relacionados às atividades centrais da empresa. Incluem:
a. os: ordens de serviço e atendimentos técnicos;
b. itensos: itens associados à OS, incluindo diagnósticos, soluções e
técnicos responsáveis;
c. venda e itensvenda: registros de vendas realizadas e produtos
comercializados;
d. ps: catálogo de produtos e serviços;
e. oc e itemoc: ordens de compra e itens adquiridos;
f. caixa: movimentações financeiras diárias.
2. Domínio cadastral: Tabelas que armazenam dados de referência
relativamente estáveis, utilizados em diversos processos operacionais:
a. pessoa: cadastro unificado de clientes, funcionários e fornecedores;
b. aparelho, marca, modelo: informações sobre os dispositivos atendidos;
c. centrocusto, tipocusto, tipopessoa: classificações e categorias
auxiliares;
d. registroponto: controle de jornada de trabalho dos funcionários.
3. Domínio financeiro: Tabelas voltadas para a gestão financeira e contábil da
empresa:
a. titulo: controle de contas a pagar e a receber;
4. Domínio de governança e comunicação: Tabelas voltadas para controle de
permissões, conteúdos internos e comunicação:
a. tblpermissao, tblpermissaopag, permissao: controle de acesso por
usuário;
b. mural, texto: informações e avisos internos da empresa.

## 2.3.2. Métodos de coleta de dados

Diante das limitações do sistema ERP atual, optou-se pela coleta de dados
via exportação manual de arquivos no formato .csv diretamente pela ferramenta
Navicat 8. Essa abordagem permite viabilidade técnica no curto prazo e oferece
flexibilidade para tratamento e transformação dos dados em etapas posteriores.

## 2.3.3. Plano de coleta estruturado

Cronograma de coleta

- Fase de coleta inicial: Será realizada uma extração completa do histórico de
dados, com o objetivo de construir uma base de referência inicial para
análises retroativas.
- Fase de atualização incremental: Estão previstos ciclos mensais de
atualização dos dados, com extração apenas dos registros modificados ou
adicionados desde a última coleta.
Responsabilidades
- Responsável pela extração: Executa a coleta conforme o cronograma,
verifica a integridade dos arquivos exportados e realiza os registros
necessários.
- Responsável pela validação: Realiza auditorias periódicas na qualidade dos
dados coletados, detectando e corrigindo eventuais inconsistências.

## 2.3.4. Estratégia de armazenamento de dados
A estratégia de armazenamento será baseada na arquitetura em camadas,
também conhecida como medallion architecture, amplamente adotado em projetos
de Business Intelligence. Os dados serão processados em quatro camadas distintas,
cada uma com objetivos específicos:

| Camada | Objetivo | Ferramenta |
|--------|----------|------------|
|Bruta (raw) |Preservar os dados originais sem modificações para rastreabilidade. | Azure Data Lake Storage (ADLS) |
|Inicial (staging) |Padronização estrutural (tipos de dados, nomenclatura, limpeza básica). | dbt (Data Build Tool) e SQL |
|Intermediária (intermediate) |Aplicação de regras de negócio e pré-modelagem dimensional. |dbt (Data Build Tool) e SQL |
|Analítica (mart) | Modelagem dimensional final (Star Schema) para consumo no Power BI. | Microsoft Power BI |

## 2.3.5. Métodos de organização e classificação dos dados

Os dados serão organizados com base na modelagem dimensional, adotando a
estrutura estrela (star schema). Nesse modelo, os dados são divididos em:
- Tabelas fato: Armazenam os eventos transacionais do negócio (como ordens
de serviço, vendas e lançamentos financeiros), com atributos quantitativos e
relacionamentos com múltiplas dimensões.
- Tabelas dimensão: Armazenam dados descritivos e de referência (como
clientes, produtos, técnicos e tempo), permitindo análises detalhadas sob
diferentes perspectivas.

Essa abordagem é recomendada para projetos de Business Intelligence por sua
simplicidade, facilidade de leitura e desempenho nas consultas analíticas, conforme
defendem Kimball e Ross (2013).

## 2.4. Análise de dados e registro de informações
Ações:
1 - Escolha das ferramentas de análise:
- Power BI: O Power BI será a ferramenta principal para visualização de dados e criação de dashboards interativos. Ele permitirá a análise em tempo real de KPIs, a criação de gráficos e relatórios interativos e facilitará a tomada de decisão estratégica. 
- dbt (Data Build Tool): O dbt será a principal ferramenta para o tratamento e transformação dos dados. Com o dbt, será possível criar pipelines de dados que limpam, estruturam e transformam dados de maneira eficiente, criando tabelas e modelos otimizados para análise. O dbt permite a aplicação de regras de negócios e a modelagem dimensional antes de enviar os dados para o Power BI. Além disso, ele possibilita versionamento e documentação das transformações de dados, o que ajuda na governança e confiabilidade dos dados.

2 - Estratégia de análise:
- Análise de tendências: Usando o Power BI, será possível analisar padrões ao longo do tempo (por exemplo, volume de reparos, tipos de defeitos mais frequentes, e tempo médio de reparo), ajudando a prever mudanças no comportamento e permitindo que a empresa se antecipe a possíveis gargalos.
- Segmentação de clientes: O dbt será utilizado para transformar e organizar os dados de clientes, criando agrupamentos baseados em comportamentos como histórico de serviços, tipo de videogame, e tempo de resposta. O Power BI ajudará a visualizar esses segmentos e gerar insights sobre as preferências de compra e necessidades de manutenção de cada grupo de clientes.
- Modelagem preditiva: Através do Power BI, utilizando os dados tratados com o dbt, será possível realizar análises preditivas para estimar o tempo de reparo de diferentes tipos de defeitos ou prever a demanda por determinadas peças. Isso permitirá otimizar os processos internos e reduzir tempos de espera.
- Análise de correlação: O Power BI facilitará a análise de correlação entre variáveis (por exemplo, tempo de reparo e tipo de defeito), permitindo a identificação de fatores que afetam o desempenho operacional. A partir disso, ajustes poderão ser feitos para reduzir falhas e melhorar a produtividade.
- Análise de KPI e métricas operacionais: Com o Power BI, os KPIs essenciais, como o Tempo Médio de Reparação, Taxa de Retrabalho  e Taxa de Conversão de Orçamentos, serão visualizados de forma clara e acessível. Isso permitirá que a equipe de gestão acompanhe o desempenho e tome decisões baseadas em dados.

3 - Geração de Insights
- Respostas para KIQs sobre tempo de manutenção e reparo: O Power BI poderá identificar quais tipos de reparos são mais demorados e quais fatores (como tipo de defeito ou modelo de videogame) impactam no tempo de reparo. O dbt ajudará a estruturar os dados de forma que permita calcular métricas como "tempo médio de reparo" por tipo de defeito.
- Respostas sobre a produtividade da equipe técnica: O dbt processará os dados dos técnicos para calcular o desempenho, como o número de reparos feitos por período e a taxa de retrabalho. O Power BI ajudará a visualizar o desempenho de cada técnico e identificar quais técnicos precisam de mais treinamento ou recursos.
- Respostas sobre a disponibilidade de peças: Com o tratamento de dados realizado no dbt, será possível verificar a relação entre a falta de peças e o impacto no tempo de reparo. O Power BI permitirá visualizar a disponibilidade de estoque e as taxas de ruptura, ajudando a melhorar o gerenciamento de peças.
- Identificação de gargalos: O Power BI pode identificar onde estão os gargalos no processo de manutenção, como atrasos devido à falta de peças ou ineficiência no diagnóstico inicial. Com essas informações, a equipe pode intervir para otimizar esses processos.

Relatório:
1 - Ferramentas utilizadas para análise:
- Power BI: Utilizado para a visualização e criação de dashboards dinâmicos com KPIs, tendências e métricas de desempenho.
- dbt (Data Build Tool): Utilizado para o tratamento e transformação dos dados, garantindo a limpeza, padronização e modelagem dimensional dos dados antes da análise.

2 - Justificativa da escolha das ferramentas de análise:
- Power BI: O Power BI foi escolhido por sua capacidade de criar visualizações ricas e interativas que ajudam na análise de dados operacionais e financeiros. Sua capacidade de gerar dashboards dinâmicos facilitam a disseminação de insights para equipes e stakeholders em tempo real. Além disso, a flexibilidade para realizar análise de dados em tempo real e a facilidade de utilização são fundamentais para a agilidade nas decisões.
- dbt: O dbt foi escolhido pela sua abordagem orientada a dados para transformação e modelagem de dados. Ele permite que as equipes de dados criem pipelines eficientes e escaláveis, além de garantir que as transformações sejam bem documentadas e versionadas. Isso é essencial para a governança dos dados e para garantir que os dados enviados para o Power BI estejam sempre limpos e organizados, o que aumenta a confiabilidade e a precisão das análises.

## 2.5. Disseminação e utilização das informações
A disseminação eficaz das informações é essencial para que os insights
gerados pelo processo de Inteligência Competitiva influenciem as decisões da
empresa de forma estratégica. Para esse fim, foram selecionadas as ferramentas
Power BI e PowerPoint, que oferecem formatos versáteis de apresentação, como
dashboards, relatórios interativos e apresentações executivas, adaptando-se às
diferentes necessidades dos tomadores de decisão.
- Power BI: O Power BI será utilizado como ferramenta central para a criação
de dashboards e relatórios interativos. Sua conexão será estabelecida com a
camada analítica do Data Lake, permitindo que os dados previamente
estruturados e tratados possam ser facilmente visualizados pelos gestores.
Como o processo de atualização não será automatizado, a alimentação dos
dashboards ocorrerá conforme ciclos previamente definidos, seguindo o
cronograma estabelecido para a extração manual dos dados em formato .csv
e sua posterior ingestão na plataforma Azure.

Para assegurar que as informações produzidas sejam efetivamente
incorporadas ao processo decisório da empresa, estão previstas as seguintes ações:
- Validação e feedback dos usuários internos: Realização de testes e
sessões de validação com os tomadores de decisão, com o objetivo de
ajustar os dashboards e relatórios às necessidades reais da organização.
- Rotina de atualização e monitoramento: Definição de ciclos regulares de
atualização dos relatórios e dashboards, de acordo com o planejamento
técnico da coleta e ingestão dos dados. Essa rotina permitirá o
monitoramento contínuo da qualidade das informações, possibilitando ajustes
e melhorias ao longo do tempo.

Para garantir que os dados estejam disponíveis no momento certo para
subsidiar decisões estratégicas, foram estabelecidas as seguintes práticas:
- Atualização programada: Como a atualização será realizada por ciclos de
extração manual, será definido um cronograma fixo para garantir
previsibilidade no acesso aos dados atualizados, alinhando as entregas às
principais rotinas de gestão da empresa.
- Notificações: A cada nova atualização dos dashboards, serão enviadas
comunicações por e-mail, informando a disponibilização das informações, de
forma a garantir que os tomadores de decisão tenham acesso aos dados no
momento oportuno.
- Agenda de reuniões estratégicas: Serão definidas agendas periódicas de
reuniões com base nas informações mais recentes disponibilizadas,
possibilitando que os insights gerados contribuam diretamente para os
processos de revisão de desempenho, planejamento e definição de metas.
Com essas medidas, garante-se que os insights produzidos pelo sistema de
Business Intelligence (BI) sejam acessíveis, compreensíveis e estrategicamente
relevantes, contribuindo para a melhoria contínua dos processos organizacionais e
para a consolidação de uma cultura empresarial orientada por dados.

## 2.6. Avaliação do processo de Inteligência Competitiva

## 2.6.1 Revisão da eficiência do processo de coleta e análise.

O processo de construção do Plano de Inteligência Competitiva demonstrou
coerência entre as etapas propostas e os objetivos estratégicos da empresa. A
identificação das necessidades de decisão, seguida da definição do KIT e
formulação das KIQs, possibilitou um mapeamento preciso dos principais pontos
críticos da operação.
A estruturação das perguntas estratégicas foi acompanhada por um
levantamento detalhado dos dados necessários, suas fontes, formas de visualização
e avaliação de disponibilidade. A escolha da extração manual dos dados via
arquivos .csv diretamente do ERP mostrou-se viável neste primeiro momento,
possibilitando acesso aos dados essenciais mesmo na ausência de automações.
A adoção de uma arquitetura de armazenamento em camadas (medallion
architecture) e a proposta de modelagem dimensional (star schema) reforçaram a
eficiência do processo, preparando o ambiente para a análise estruturada e
escalável dos dados.

## 2.6.2. Feedback dos usuários finais
A validação do Plano de Inteligência Competitiva será realizada pelo
proprietário da Eletronic Games, que já analisou a proposta e manifestou aprovação
quanto à sua aplicabilidade e relevância para o contexto da empresa. De acordo
com sua avaliação preliminar, o plano atende plenamente às expectativas,
oferecendo um mapeamento claro e bem estruturado das informações críticas para
a gestão da assistência técnica.
O proprietário destacou que os indicadores propostos são altamente
compatíveis com a realidade operacional da organização, apresentando potencial
para gerar insights relevantes tanto para decisões operacionais quanto para o
planejamento estratégico. A clareza das perguntas de inteligência e sua adequação
às rotinas internas foram apontadas como diferenciais positivos da proposta.
Além disso, o gestor demonstrou entusiasmo com a futura implementação dos
dashboards no Power BI, ressaltando a importância de manter a equipe alinhada a
uma cultura orientada por dados, como fator essencial para o sucesso do projeto.
Entre os principais pontos positivos apontados estão:
- Visibilidade sobre a produtividade individual e coletiva da equipe técnica;
- Compreensão mais clara sobre gargalos no processo de manutenção;
- Possibilidade de planejamento mais assertivo da reposição de peças e
insumos.
## 2.6.3. Potenciais desafios
Com base na análise do contexto e características técnicas do projeto, é possível
antecipar alguns desafios que poderão surgir durante a implementação do Plano de
Inteligência Competitiva:
- Integração limitada do sistema de ERP: A ausência de APIs ou conectores
nativos poderá dificultar a automatização da extração de dados, tornando o
processo mais dependente de rotinas manuais por meio de arquivos .csv. Tal
limitação poderá impactar negativamente a escalabilidade e a confiabilidade
do fluxo de dados.
- Qualidade e padronização dos dados: Existe o risco de inconsistências nos
dados históricos, presença de campos preenchidos de forma livre e ausência
de categorização padronizada, fatores que podem dificultar o tratamento e a
modelagem das informações na etapa de transformação.
-Falta de documentação da estrutura do banco de dados: A inexistência de
um dicionário de dados formal poderá comprometer a compreensão da base
por parte de novos integrantes da equipe de dados, além de dificultar futuras
manutenções e evoluções da arquitetura da informação.
## 2.6.4. Melhoria contínua
Com base na análise crítica do planejamento proposto, são apresentadas
recomendações para o aprimoramento contínuo da futura implementação do
processo de Inteligência Competitiva:
-  Estabelecimento de um plano de governança de dados: Definir padrões
para nomenclatura de campos, validação de registros, periodicidade de
atualização e atribuição de responsabilidades, com o objetivo de garantir a
integridade e a confiabilidade das informações ao longo do tempo.
- Automatização progressiva do processo de coleta: Avaliar a viabilidade de
implementação futura de mecanismos de automação para a extração e
ingestão dos dados, com o objetivo de reduzir a dependência de processos
manuais e ampliar a frequência de atualização dos relatórios.
- Documentação da estrutura do banco de dados: Desenvolver um
dicionário de dados contendo a descrição de tabelas, campos,
relacionamentos e regras de negócio, promovendo maior transparência e
facilitando a manutenção do modelo de dados.
- Criação de rotinas de validação e atualização contínua: Estabelecer
pontos de controle periódicos para revisão da qualidade dos dados,
atualização dos dashboards e ajustes nas análises conforme o uso prático e
os feedbacks dos usuários.
- Capacitação sobre indicadores e dashboards: Promover treinamentos
periódicos com os gestores e com a equipe técnica, com foco na
interpretação dos indicadores, no uso adequado das visualizações e na
aplicação prática dos insights gerados para a melhoria da operação.

## 2.7. Compliance de TI e Segurança da Informação

Este tópico tem como objetivo garantir que os processos de Inteligência
Competitiva (IC) da Electronic Games BH estejam em conformidade com as
legislações vigentes e as melhores práticas em segurança da informação. A
conformidade com normas como a Lei Geral de Proteção de Dados (LGPD), bem
como a adoção de políticas estruturadas de segurança, é essencial para assegurar a
integridade, a confidencialidade e a disponibilidade dos dados tratados.

## 2.7.1. Mapeamento de normas e regulamentações aplicáveis

O uso de dados pessoais e sensíveis no contexto empresarial exige atenção
aos seguintes marcos regulatórios:

**Lei Geral de Proteção de Dados (LGPD)**

A LGPD (Lei nº 13.709/2018) regula o tratamento de dados pessoais no Brasil
e estabelece princípios como:

- Finalidade e transparência na coleta e tratamento de dados;
- Consentimento do titular dos dados;
- Segurança e prevenção contra vazamento de informações;
- Direitos do titular, incluindo acesso, correção e exclusão de dados;
- Responsabilização e prestação de contas pelas empresas que tratam dados
pessoais.

A LGPD impacta diretamente a operação da Eletronic Games, uma vez que
seus sistemas armazenam e processam dados pessoais de clientes, fornecedores e
funcionários. Assim, medidas de compliance precisam ser implementadas para
garantir a conformidade com essa legislação.

## 2.7.2. Políticas de proteção de dados e segurança da informação

Para minimizar riscos, a empresa deve adotar estratégias como anonimização
e pseudonimização dos dados sensíveis, garantindo que as informações pessoais
não possam ser vinculadas diretamente a indivíduos. Essa abordagem auxilia a
organização a ficar em compliance com a LGPD.

O armazenamento de dados deve ser restrito ao essencial, utilizando
criptografia avançada para que somente usuários autorizados tenham acesso. Além
disso, procedimentos de exclusão segura devem ser implementados para eliminar
permanentemente informações que não são mais necessárias.

O controle de acessos deve ser rigoroso, empregando autenticação de dois
fatores (2FA) e concessão de permissões de acordo com a função do usuário. O
registro detalhado de acessos e modificações a partir dos logs nos sistemas deve
ser mantido para auditorias futuras, e revisões periódicas das permissões devem
garantir que funcionários desligados ou sem necessidade de acesso não possam
manipular os dados. Estratégias para identificar e bloquear acessos não autorizados
ou suspeitos também devem ser estabelecidas.

No que se refere à transferência e armazenamento de dados, é fundamental
utilizar criptografia tanto em repouso quanto em trânsito, além de garantir conexões
seguras (SSL/TLS) para a transmissão de informações sensíveis. Backups regulares
devem ser realizados, juntamente com procedimentos de recuperação de desastres
para assegurar a continuidade das operações. O monitoramento de tráfego deve ser
constante para identificar atividades incomuns e possibilitar respostas rápidas a
incidentes. Métodos de armazenamento descentralizado e replicação de dados
devem ser considerados para aumentar a resiliência e reduzir os impactos de falhas
técnicas.

## 2.7.3. Auditoria e conformidade

Para manter a conformidade, a empresa deve realizar auditorias regulares,
avaliando a segurança da informação, monitorando tentativas de acesso indevido e
documentando vulnerabilidades e medidas corretivas adotadas. O uso de
ferramentas especializadas em análise de vulnerabilidades auxilia na detecção de
falhas antes que possam ser exploradas. Além disso, deve ser estabelecido um
plano de resposta a incidentes para garantir ações ágeis e eficazes diante de
eventuais violações de segurança.

A capacitação dos colaboradores desempenha um papel fundamental na
segurança da informação. Treinamentos frequentes sobre boas práticas, gestão de
senhas e atualizações de sistemas são essenciais. Simulações de ataques podem
ser conduzidas para testar a conscientização da equipe e identificar pontos de
melhoria. Campanhas internas também devem reforçar a importância da segurança
de dados, e treinamentos específicos por nível hierárquico ajudarão na
disseminação de responsabilidades dentro da organização.





