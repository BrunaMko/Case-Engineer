**Projeto ETL Orçamento Estado de São Paulo 2019**



*Descrição*

Este projeto implementa um processo de ETL (Extract, Transform, Load) para processar dados de orçamento do Estado de São Paulo de 2019. O processo envolve a extração de dados de arquivos CSV, a transformação para ajustar tipos de dados e corrigir formatações, e o carregamento dos dados tratados em um banco de dados SQL Server.



*Passos do Processo de ETL*

1. Extração (Extract)
   
Os dados são extraídos de dois arquivos CSV: gdvDespesasExcel.csv e gdvReceitasExcel.csv.
Utiliza-se Pandas para ler os arquivos CSV e carregar os dados em estruturas de dados pandas DataFrame.

2. Transformação (Transform)
   
Despesas:
Limpeza dos dados: remoção de linhas nulas.
Conversão do formato de valores monetários para float, removendo pontos e substituindo vírgulas.

Receitas:
Limpeza dos dados: remoção de linhas nulas.
Conversão do formato de valores monetários para float, removendo pontos e substituindo vírgulas.

Integração:
Combinação (merge) dos dados de despesas e receitas com base na coluna "Fonte de Recursos", usando um join do tipo outer para preservar todos os dados.


3. Carga (Load)
 
Os dados transformados são carregados em tabelas separadas no banco de dados SQL Server.
Utiliza-se SQLAlchemy para criar uma conexão com o banco de dados e Pandas para enviar os DataFrames diretamente para o SQL Server.



*Requisitos*

Python 3.x

Bibliotecas: pandas, sqlalchemy, pyodbc

Banco de Dados SQL Server
