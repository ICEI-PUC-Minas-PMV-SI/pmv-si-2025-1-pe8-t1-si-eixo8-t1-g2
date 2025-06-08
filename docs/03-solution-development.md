3.6. Viabilidade técnica e financeira da estrutura desenvolvida

	Através da análise, são apresentados os recursos tecnológicos utilizados na solução proposta, acompanhados de uma análise técnica e financeira que demonstra a viabilidade de sua adoção pela empresa.

 3.6.1. Estrutura Tecnológica Adotada
A arquitetura proposta para o sistema de Business Intelligence contempla três componentes principais:
**Armazenamento de dados:** Banco de dados relacional MySQL Flexível (Azure).


**Transformação de dados:** Ferramenta de transformação dbt Core (versão CLI).


**Visualização de dados:** Power BI Desktop para criação de dashboards locais.

Essa estrutura foi escolhida por sua compatibilidade com a nuvem, escalabilidade progressiva e uso gratuito de ferramentas open-source. Além disso, o volume atual de dados da empresa é relativamente pequeno, com aproximadamente 800MB de dados, o que permite iniciar a operação com uma configuração leve e de baixo custo.

O monitoramento de custo e uso será feito por meio do Azure Cost Management, permitindo ajustes dinâmicos conforme o crescimento do volume de dados e acessos.


3.6.2. Justificativa Técnica das Escolhas

Componente
Justificativa Técnica
MySQL Flexível (Azure)
Suporte à escalabilidade, backup automático, alta disponibilidade e integração com ferramentas nativas da Microsoft. A capacidade inicial é suficiente para hospedar os 800MB de dados atuais, com margem para expansão futura.
dbt Core
Ferramenta open-source de transformação de dados com versionamento de modelos e modularidade. Pode ser executada localmente, sem custos adicionais
Power BI Desktop
Solução amplamente adotada para visualização de dados, com alto poder de criação de dashboards e sem custos iniciais de licenciamento. Ideal para análise local de dados.


3.6.3. Estimativa de Custo Mensal

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


3.6.4. Escalabilidade e cenários de custo

Cenário de Uso
Estimativa Mensal
Fase atual (dados pequenos, sem E/S)
R$191,98
Operação com 20GB e tráfego moderado
R$ 400,00–R$ 600,00
Crescimento contínuo (com backup e E/S)
R$ 800,00–R$ 1.200,00



3.6.5. Conclusão da Viabilidade

A estrutura proposta é tecnicamente sólida, financeiramente viável e escalável. Com um custo mensal inicial inferior a R$200,00, a empresa poderá implantar um sistema de Business Intelligence completo, com visualizações interativas, controle de dados estruturado e possibilidade de crescimento conforme a demanda. Trata-se de uma solução estratégica e sustentável para suportar a evolução operacional da empres3.6.2. Justificativa Técnica das Escolhas















REFERÊNCIAS

ELETRONIC GAMES ASSISTÊNCIA TÉCNICA. Site oficial. Disponível em: 22 fev. 2025.
KIMBALL, Ralph; ROSS, Margy. The Data Warehouse Toolkit: The Definitive Guide to Dimensional Modeling. 3. ed. Indianapolis: Wiley Publishing, 2013.
















