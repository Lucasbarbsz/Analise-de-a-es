# 📈 Análise Comparativa: Ações Brasileiras vs Ibovespa

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green?style=flat-square&logo=pandas)
![Status](https://img.shields.io/badge/Status-Completo-brightgreen?style=flat-square)

---

## 📌 Visão Geral

Projeto de análise quantitativa e visualização de dados que compara o desempenho de **8 ações brasileiras** com o índice **Ibovespa** utilizando dados históricos de 5 anos. O estudo identifica padrões de performance, ativos outperformers e oportunidades de investimento através de análise estatística e visualizações interativas.

**Use Case Real:** Análise típica realizada por analistas de dados e quants no mercado financeiro brasileiro.

---

## 🎯 Objetivos do Projeto

✅ **Coleta e integração** de dados financeiros em tempo real via API  
✅ **Tratamento e limpeza** de séries temporais financeiras  
✅ **Cálculo de retornos** anuais e cumulativos  
✅ **Análise comparativa** de performance vs. benchmark  
✅ **Visualização exploratória** de tendências e padrões  
✅ **Geração de insights** para decisões de investimento  

---

## 📊 Ativos Analisados

| Ativo | Setor | Tipo |
|-------|-------|------|
| **ALOS3.SA** | Utilidade Pública | Ação |
| **BBAS3.SA** | Financeiro | Ação |
| **BBSE3.SA** | Financeiro | Ação |
| **BRBI11.SA** | Financeiro | FII |
| **CMIG4.SA** | Utilidade Pública | Ação |
| **CXSE3.SA** | Varejo | Ação |
| **LEVE3.SA** | Manufatura | Ação |
| **^BVSP** | Índice de Referência | Benchmark |

---

## 🛠️ Stack Tecnológico

```
📦 Data Processing:     Python, Pandas, NumPy
📊 Visualização:        Matplotlib, Seaborn
🌐 Fonte de Dados:      yfinance (Yahoo Finance API)
📓 Ambiente:            Jupyter Notebook
```

---

## 🔍 Metodologia

### 1️⃣ **Coleta de Dados**
- Extração de histórico de preços via `yfinance`
- Período de análise: **últimos 5 anos**
- Frequência: **dados diários** com agregação anual

```python
import yfinance as yf

tickers = ["ALOS3.SA", "BBAS3.SA", "BBSE3.SA", "BRBI11.SA", 
           "CMIG4.SA", "CXSE3.SA", "LEVE3.SA", "^BVSP"]

dados = yf.download(tickers, period='5y')['Close']
```

### 2️⃣ **Processamento e Preparação**
- Tratamento de valores ausentes
- Agregação para frequência anual (último preço do ano)
- Normalização de datas

```python
dados_anuais = dados.resample('Y').last()
retornos = dados_anuais.pct_change() * 100
```

### 3️⃣ **Análise Estatística**
- Cálculo de retornos simples e acumulados
- Métricas de risco-retorno
- Comparação de performance vs. benchmark

### 4️⃣ **Visualização e Insights**
- Gráficos de séries temporais
- Análise de evolução de investimento
- Identificação de outperformers e underperformers

---

## 📈 Principais Insights

O projeto gera análises como:
- 🏆 **Ativos com melhor performance** anual
- 📊 **Comparação de volatilidade** entre títulos
- 📉 **Retornos acumulados** vs. benchmark
- 🔄 **Correlação entre ativos** e tendências

---

## 🚀 Como Usar

### Pré-requisitos
```bash
pip install pandas numpy matplotlib seaborn yfinance jupyter
```

### Executar a Análise
1. Clone o repositório
2. Abra `Analise_acoes.ipynb` no Jupyter Notebook
3. Execute as células na sequência (as dependências são carregadas automaticamente)
4. Visualize os gráficos e tabelas geradas interativamente

---

## 📁 Estrutura do Projeto

```
Projeto_analise_ações/
│
├── 📓 Analise_acoes.ipynb    ← Análise completa (coleta → visualização)
├── 📄 README.md               ← Documentação
└── 📊 dados/                  ← Dados brutos (se salvos localmente)
```

---

## 🎓 Conceitos Aplicados

- ⏰ **Séries Temporais Financeiras:** Tratamento de dados históricos de preços
- 💹 **Retornos Financeiros:** Cálculo de retorno simples e logarítmico
- 📊 **Análise Exploratória (EDA):** Identificação de padrões e anomalias
- 🔗 **Integração de APIs:** Consumo de dados em tempo real via yfinance
- 📈 **Visualização de Dados:** Gráficos informativos para comunicação de resultados

---

## 💡 Possíveis Extensões

- Adicionar **modelos de regressão** para previsão de preços
- Implementar **estratégias de backtesting** de carteiras
- Calcular **métricas avançadas** (Sharpe Ratio, Value at Risk)
- Criar **dashboards interativos** com Plotly ou Dash
- Automatizar a **coleta e atualização de dados**

---

## 📬 Contato

Interessado em dados? Vamos conversar!

📧 [Email] | 💼 [LinkedIn] | 🐙 [GitHub]

---

**Desenvolvido para análise educacional e demonstração de habilidades em ciência de dados.**