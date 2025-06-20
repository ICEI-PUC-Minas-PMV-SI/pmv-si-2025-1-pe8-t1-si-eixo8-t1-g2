# 4. PETI, GOVERNANÇA E AUDITORIA DE TI

## 4.1. PETI (Plano Estratégico de Tecnologia da Informação)
O Plano Estratégico de Tecnologia da Informação (PETI) tem como finalidade dar continuidade ao uso estratégico da TI na Eletronic Games, apoiando a gestão da empresa com informações confiáveis e relevantes, geradas a partir de seus próprios dados operacionais. A TI deve contribuir diretamente para a melhoria da eficiência dos serviços, da tomada de decisão baseada em dados e da organização dos processos internos.

## 4.1.1 Pontos fortes e limitações

 ## Pontos fortes identificados:
 
- Implantação de dashboards em Power BI com indicadores operacionais relevantes;
- Organização da base de dados com modelagem dimensional (star schema);
- Uso do dbt para tratamento e transformação dos dados;
- Apoio da TI na tomada de decisão estratégica com métricas como tempo de reparo, produtividade técnica e controle de estoque;
- Engajamento da gestão com a cultura orientada a dados;
- Existência de controle de acesso por nível de usuário no ERP;
- Realização de backups diários do banco de dados.
 
## Limitações enfrentadas:

- O servidor local usa Windows Vista e MySQL 5, o que inviabilizou o uso de ferramentas modernas como Python;
- Exportação via .csv falhou devido a colunas com textos extensos e caracteres como “;” (termos de garantia);
- Dumps gerados pelo Navicat 8 estavam incompletos;
- Foi necessário criar scripts .bat com comandos MySQL para exportação/importação confiável no MySQL Flexível (Azure);
- Durante a importação para o MySQL 8, foi preciso:
   -Alterar a engine do banco e tabelas para InnoDB;
   -Corrigir codificação para UTF-8;
   -Converter formatos de data obsoletos;
- Presença de campos com texto livre (ex: descrição do orçamento), dificultando categorização e análise;
- Inexistência de automação no fluxo de dados entre o ERP e o BI (Power BI).
  
## 4.1.2 Diretrizes estratégicas de TI

- Migrar o banco de dados local (MySQL 5) para o MySQL 8 na nuvem (Azure), assegurando performance, segurança e escalabilidade;
- Atualizar a engine do banco/tabelas para InnoDB;
- Automatizar a ingestão de dados conectando a base ao dbt e ao Power BI;
- Substituir os scripts .bat por scripts Python, permitindo automação e manutenção facilitada;
- Avaliar o uso de ferramentas de orquestração como Apache Airflow ou Azure Data Factory para controlar os pipelines de dados;
 -Implementar criptografia de senhas (hash + salt) no banco;
 -Substituir campos livres por categorias padronizadas (ex: tipo de orçamento);
- Incluir os backups diários em um plano de contingência com restauração documentada;
- Consolidar o Power BI como ferramenta decisória, com novos indicadores voltados para produção, equipe técnica e vendas/faturamento.
  
##  4.1.3 Objetivos estratégicos de TI

## Curto prazo (0 a 6 meses):

- Padronizar estrutura dos dados no banco;
- Categorizar campos de texto livre;
- Implementar criptografia de senhas;
- Criar manual de uso do sistema e dashboards;
- Substituir scripts .bat por script Python básico.
  
## Médio prazo (6 a 12 meses):

- Migrar banco para MySQL 8 (Azure);
- Automatizar ingestão diária de dados com Python;
- Avaliar e implementar orquestrador de dados (Airflow, Azure Data Factory);
- Expandir dashboards com métricas de produção, técnicos e faturamento;
- Documentar arquitetura analítica e base de dados.
  
## Longo prazo (1 a 2 anos):

- Integrar ERP e BI em tempo quase real;
- Implementar análises preditivas (ex: previsão de demanda);
- Promover treinamentos sobre cultura de dados e interpretação de dashboards;
- Realizar revisões trimestrais com base nos indicadores estratégicos.
  
## 4.1.4 Indicadores de acompanhamento

Para avaliar a evolução da TI e o impacto do BI na operação da Eletronic Games, propõem-se os seguintes indicadores:

- Número de usuários ativos no Power BI e ERP;
- Frequência de atualização dos dados (meta: ingestão diária automatizada);
- Tempo médio entre captura do dado e exibição no dashboard;
- Redução do Tempo Médio de Reparo (TMR);
- Redução da Taxa de Retrabalho (TR);
- Taxa de sucesso da ingestão automatizada;
- Percentual de senhas protegidas por criptografia;
- Percentual de campos livres transformados em categorias;
- Aumento no uso dos indicadores de produção, técnicos e faturamento nas decisões.

## 4.2 Auditoria e Governança de TI

## 4.2.1 Governança de TI

## Modelo baseado na norma ISO/IEC 38500

A norma ISO/IEC 38500 orienta a governança de TI com base em 6 princípios:

1. Responsabilidade

- Responsáveis definidos para rotinas de backup, ingestão de dados, dashboards e infraestrutura;
- Presença de controle de acesso por nível no sistema ERP;
- Papéis técnico e administrativo estabelecidos para garantir continuidade.
  
2. Estratégia

- PETI com objetivos de curto, médio e longo prazo;
- Diretrizes estratégicas incluem migração do banco local para o Azure (MySQL 8 + InnoDB), automação com dbt e Power BI, criptografia de senhas, categorização de campos e orquestração de dados com Airflow ou Azure Data Factory.
  
3. Aquisição

- Ferramentas escolhidas de acordo com orçamento: Power BI, dbt, MySQL, scripts .bat;
- Proposta de migração para scripts Python e uso futuro de orquestradores;
- Armazenamento seguro (Azure Storage, Google Drive, etc).

4. Desempenho

- Indicadores monitorados: TMR, retrabalho, ingestão, usuários ativos, segurança, categorização;
- Revisões periódicas para manter alinhamento da TI com o negócio.

5. Conformidade

- Correção de falhas críticas como criptografia, engine de banco, codificação, backup validado;
- Alinhamento com boas práticas e aderência básica à LGPD.

6. Comportamento humano

- Manual de uso e vídeo tutorial para novos colaboradores;
- Treinamentos e incentivo à cultura orientada a dados;
- BI como ferramenta ativa na rotina de decisões.

## Modelo baseado no COBIT

Governance Domain – EDM (Evaluate, Direct, Monitor)

EDM01 – Estrutura de governança definida:
PETI documentado com responsabilidades, metas e prioridades. Governança simplificada, acessível e alinhada ao porte da empresa.

EDM02 – Entrega de benefícios:
Dashboards operacionais entregam valor direto à empresa. Métricas relevantes são usadas na operação e gestão.

EDM03 – Riscos otimizados:
Problemas com dump, segurança de senhas, campos desestruturados e backups foram resolvidos.
 Plano de contingência implementado.
 
## Management Domains – APO, BAI, DSS, MEA

APO03 – Arquitetura corporativa gerenciada:
Banco atualizado (MySQL 8 + InnoDB), codificação ajustada, categorização aplicada, nuvem adotada (Azure).
BAI01 – Programas e projetos gerenciados:
Execução do PETI por etapas. Metas bem definidas para automação, integração e melhorias contínuas.
BAI09 – Ativos gerenciados:
Banco, backups, scripts e dashboards sob controle com rotinas de verificação e documentação mínima.
DSS01 – Operações gerenciadas:
Execução diária de scripts e backups. Em andamento substituição por automações Python.
DSS04 – Continuidade garantida:
Backup diário, testes de restauração, plano simples de contingência com ferramentas acessíveis.
MEA01 – Avaliação de desempenho e conformidade:
Indicadores estratégicos para TI e BI monitorados com revisões periódicas para ajustes.

## 4.2.2 Segurança e proteção de dados

A segurança e proteção dos dados na Eletronic Games é estruturada com base em dois pilares: gestão de segurança conforme a norma ISO/IEC 27001 e referência em práticas do NIST Cybersecurity Framework (CSF). Essa abordagem garante proteção integral dos dados pessoais e operacionais, bem como resiliência contra ameaças digitais.

## Gestão de segurança da informação – ISO/IEC 27001

A Eletronic Games adota diretrizes da ISO 27001 para estabelecer um Sistema de Gestão da Segurança da Informação (SGSI), considerando os seguintes controles:

- Política de segurança: Diretrizes definidas para acesso a sistemas, armazenamento seguro e comportamento digital;
- Controle de acesso: Níveis de permissão diferenciados por função no ERP e dashboards; em implantação autenticação com senha criptografada (hash + salt);
- Criptografia: Uso previsto de criptografia para armazenamento e transmissão segura de dados sensíveis;
- Gestão de ativos: Inventário de ativos tecnológicos sob gestão (banco de dados, dashboards, scripts, backups);
- Backup e continuidade: Backups diários com plano básico de recuperação testado periodicamente;
- Segurança física e do ambiente: Adoção de nuvem (Azure) reduz exposição do servidor físico obsoleto;
- Segurança na aquisição e desenvolvimento: Scripts e pipelines documentados e mantidos com versionamento;
- Conscientização e capacitação: Capacitações planejadas sobre segurança e boas práticas digitais.

## Framework de Cibersegurança do NIST (CSF)

A Eletronic Games estrutura sua proteção cibernética segundo os cinco pilares do NIST:

- Identify (Identificar): Mapeamento de ativos de TI e dados sensíveis (dados pessoais, operacionais e financeiros);
- Protect (Proteger): Adoção de controles de acesso, criptografia, segmentação de dados e uso de scripts auditáveis;
- Detect (Detectar): Verificação periódica de integridade dos dados e alertas sobre falhas de ingestão;
- Respond (Responder): Plano de resposta simples, com isolamento de falhas e recuperação de dados via backup;
- Recover (Recuperar): Procedimentos definidos de restauração com prioridade em dados operacionais críticos.



## REFERÊNCIAS

ELETRONIC GAMES ASSISTÊNCIA TÉCNICA. Site oficial. Disponível em: 22 fev. 2025.
KIMBALL, Ralph; ROSS, Margy. The Data Warehouse Toolkit: The Definitive Guide to Dimensional Modeling. 3. ed. Indianapolis: Wiley Publishing, 2013.
