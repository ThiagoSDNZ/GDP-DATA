# 📊 Projeto de Análise do PIB Global (2020-2025)
Projeto de Engenharia e Análise de Dados focado na evolução do Produto Interno Bruto (PIB) de diversos países, utilizando a Arquitetura Medalhão para organizar o fluxo de transformação de dados (ETL).

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data_Processing-orange)
![Architecture](https://img.shields.io/badge/Architecture-Medalhões_(Bronze--Prata--Ouro)-green)
![Visualization](https://img.shields.io/badge/Visualization-PowerBI-yellow)

## 🏗️ Estrutura do Projeto
O projeto está dividido em camadas para garantir a integridade e a rastreabilidade dos dados:

```
GDP-DATA/
│
├── 📁 data/
│   ├── 📁 1-bronze/          # Dados brutos persistidos
│   │   └── 01_bronze.ipynb
│   │   └── dados_bronze.csv
|   |
│   ├── 📁 2-prata/           # Dados limpos e transformados
│   │   └── 02_prata.ipynb
│   │   └── dados_prata.csv
|   |
│   └── 📁 3-ouro/            # Tabelas analíticas e KPIs
│       └── 03_ouro.ipynb
│       └── dados_ouro.csv
│
├── 📋 Requirements.txt       # Dependências do projeto
├── 📖 README.md              # Documentação do projeto
└── 🐍 .gitignore             # Arquivos ignorados pelo Git
```

## 🚀 O Fluxo de Dados (ETL)

### 🥉 Camada Bronze - Ingestão
- **Objetivo**: Ler o ficheiro fonte (gdp.csv) e guardá-lo num formato de fácil acesso para as próximas etapas.
- **Processo**: Importação via Pandas e gravação de um checkpoint bruto em CSV.

### 🥈 Camada Prata - Limpeza e Padronização
Nesta fase, os dados deixam de ser "crus" e tornam-se prontos para cálculos:
- **Normalização**: Colunas convertidas para snake_case e nomes traduzidos para Português.
- **Tipagem**: Conversão de valores monetários (strings) para tipos numéricos (float).
- **Tratamento de Nulos**: Utilização de interpolação linear entre os anos para preencher lacunas de forma realista.
- **Feature Engineering**: Cálculo do crescimento percentual anualizado (ano a ano) e média de crescimento do período.

### 🥇 Camada Ouro - Business Intelligence (BI)
Dados refinados para responder a perguntas de negócio:
- **Participação de Mercado**: Cálculo do peso de cada país no PIB mundial em 2020 e 2025.
- **Tendência de Participação**: Identificação de quais economias ganharam ou perderam espaço relativo no cenário global.
- **Rankings**: Classificação dos países por crescimento bruto e proporcional.
- **Categorização**: Segmentação automática dos países em faixas de crescimento (Alto, Médio, Baixo).

## 🛠️ Tecnologias Utilizadas
- **Linguagem**: Python 3.12.
- **Manipulação de Dados**: Pandas.
- **Ambiente**: Jupyter Notebook.
