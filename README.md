📊 Análise de Retornos de Ações Brasileiras vs Ibovespa
📌 Sobre o Projeto

Este projeto tem como objetivo analisar o desempenho de ações brasileiras ao longo dos anos, comparando seus retornos com o índice de referência do mercado, o Ibovespa.

A análise busca identificar padrões de performance, ativos com maior retorno e possíveis oportunidades de investimento com base em dados históricos.

🎯 Objetivos
- Calcular os retornos anuais de ações brasileiras
- Comparar o desempenho dos ativos com o Ibovespa
- Identificar ativos com melhor performance média
- Visualizar a evolução dos investimentos ao longo do tempo

📊 Ativos Analisados
ALOS3.SA
BBAS3.SA
BBSE3.SA
BRBI11.SA
CMIG4.SA
CXSE3.SA
LEVE3.SA
^BVSP (Ibovespa)

⚙️ Tecnologias Utilizadas
Python
Pandas
Matplotlib
Jupyter Notebook

🗂️ Estrutura do Projeto
analise-acoes-brasileiras/
│
├── notebook.ipynb       # Análise completa
├── dados.csv            # Base de dados
└── README.md            # Documentação

🔍 Etapas da Análise
1. Coleta de Dados

Os dados históricos dos ativos foram obtidos utilizando a API do Yahoo Finance por meio da biblioteca yfinance.

import yfinance as yf

tickers = [
    "ALOS3.SA", "BBAS3.SA", "BBSE3.SA",
    "BRBI11.SA", "CMIG4.SA", "CXSE3.SA",
    "LEVE3.SA", "^BVSP"
]

dados = yf.download(tickers, period='5y')['Close']
2. Tratamento e Preparação

Conversão de datas e agregação para frequência anual.

dados = dados.resample('Y').last()

💼 Aplicação no Mercado

Este projeto simula análises realizadas por analistas de dados e profissionais do mercado financeiro, utilizando dados reais para geração de insights estratégicos.