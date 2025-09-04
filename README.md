# Desafio Indicium - Análise de Dados IMDb

Este projeto apresenta uma análise exploratória completa do dataset IMDb contendo 999 filmes, com foco na predição de ratings. A análise inclui visualizações detalhadas, tratamento de dados ausentes, engenharia de features e modelagem preditiva.

## 📋 Visão Geral

O projeto contém:
- Análise exploratória de dados (EDA) completa
- Pré-processamento e limpeza de dados
- Engenharia de features avançada
- Modelagem preditiva com múltiplos algoritmos
- Interpretabilidade do modelo (XAI)
- Relatório detalhado em Markdown

## 🎯 Resultados Principais

- **Melhor modelo**: XGBoost com R² = 0.53
- **Feature mais importante**: No_of_Votes
- **Insights**: Meta_score é o preditor mais forte do IMDB_Rating

## 📁 Estrutura do Projeto

```
desafio/
├── README.md                    # Este arquivo
├── requirements.txt             # Dependências completas com versões exatas
├── requirements-minimal.txt     # Dependências essenciais apenas
├── LH_CD_LUCAS.ipynb           # Notebook principal com análises
├── relatorio_eda_analises.md   # Relatório completo das análises
├── xgboost_model.pkl          # Modelo XGBoost treinado
├── data/                      # Pasta com dados
│   ├── desafio_indicium_imdb.csv
│   └── [Lighthouse] Desafio Ciência de Dados 2025-11.pdf
├── catboost_info/            # Logs do CatBoost
└── img*.png                  # Gráficos gerados
```

## 🛠️ Pré-requisitos

### Sistema Operacional
- Windows 10/11
- Python 3.8 ou superior

### Ferramentas Necessárias
- Git (para clonar o repositório)
- Jupyter Notebook ou JupyterLab
- VS Code (recomendado)

## 📦 Instalação

### 1. Clone o Repositório
```bash
git clone <url-do-repositorio>
cd desafio
```

### 2. Criar Ambiente Virtual
```bash
# Criar ambiente virtual
python -m venv venv

# Ativar ambiente virtual (Windows)
.\venv\Scripts\activate

# Ou usando PowerShell
.\venv\Scripts\Activate.ps1
```

### 3. Instalar Dependências

#### Opção A: Usando requirements.txt (recomendado)
```bash
# Instalar todas as dependências com versões exatas
pip install --upgrade pip
pip install -r requirements.txt
```

#### Opção B: Usando requirements-minimal.txt (instalação mínima)
```bash
# Instalar apenas pacotes essenciais
pip install --upgrade pip
pip install -r requirements-minimal.txt
```

#### Opção C: Instalação manual
```bash
pip install --upgrade pip
pip install pandas==2.3.2 numpy==2.3.2 matplotlib==3.10.6 seaborn==0.13.2 plotly==6.3.0
pip install scikit-learn==1.7.1 xgboost==3.0.4 lightgbm==4.6.0 catboost==1.2.8
pip install optuna==4.5.0 tqdm==4.67.1 joblib==1.5.2 jupyter
```

#### Arquivos de Requisitos Disponíveis:
- **`requirements.txt`**: Todas as dependências com versões exatas (recomendado para reprodutibilidade)
- **`requirements-minimal.txt`**: Apenas pacotes essenciais (instalação mais rápida)

### 4. Verificar Instalação
```bash
python -c "import pandas, numpy, sklearn, xgboost; print('Instalação bem-sucedida!')"
```

## 🚀 Executando o Projeto

### 1. Iniciar Jupyter Notebook
```bash
# Ativar ambiente virtual
.\venv\Scripts\activate

# Iniciar Jupyter
jupyter notebook
```

### 2. Abrir o Notebook Principal
- No navegador, navegue até `LH_CD_LUCAS.ipynb`
- Execute as células sequencialmente usando `Shift + Enter`

### 3. Executar Análise Completa
O notebook está organizado nas seguintes seções:
1. **Importação de Bibliotecas e Dados**
2. **Análise Exploratória (EDA)**
3. **Pré-processamento**
4. **Engenharia de Features**
5. **Modelagem**
6. **Avaliação e Interpretabilidade**

### 4. Usar Modelo Pré-treinado
```python
import pickle
import pandas as pd

# Carregar modelo salvo
with open('xgboost_model.pkl', 'rb') as f:
    modelo = pickle.load(f)

# Fazer predições (após pré-processamento dos dados)
# predictions = modelo.predict(X_test)
```

## 📊 Dados

### Dataset Principal
- **Arquivo**: `data/desafio_indicium_imdb.csv`
- **Registros**: 999 filmes
- **Features**: 15 variáveis originais
- **Target**: IMDB_Rating

### Estrutura dos Dados
```
Series_Title          - Título do filme
Released_Year         - Ano de lançamento
Certificate          - Classificação indicativa
Runtime              - Duração em minutos
Genre                - Gênero principal
IMDB_Rating          - Rating IMDb (variável alvo)
Overview             - Sinopse
Meta_score           - Score do Metacritic
Director             - Diretor
Star1, Star2, Star3, Star4 - Atores principais
No_of_Votes          - Número de votos
Gross                - Bilheteria bruta
```

## 🔍 Principais Funcionalidades

### Análise Exploratória
- Visualizações interativas com Plotly
- Análise de correlações
- Detecção de outliers
- Análise temporal e por categorias

### Modelagem
- 6 algoritmos testados:
  - XGBoost (melhor performance)
  - LightGBM
  - Random Forest
  - CatBoost
  - Decision Tree
  - Linear Regression

### Interpretabilidade
- Feature importance
- SHAP values (se implementado)
- Análise de predições

## 📈 Resultados

### Performance dos Modelos
| Modelo | MAE | MSE | RMSE | R² |
|--------|-----|-----|------|-----|
| **XGBoost** | **445.04** | **380,569** | **616.90** | **0.603** |
| LightGBM | 450.36 | 391,657 | 625.82 | 0.591 |
| Random Forest | 460.28 | 420,645 | 648.57 | 0.561 |

### Features Mais Importantes
1. No_of_Votes (~0.032)
2. Runtime_Category_médio (~0.021)
3. MetaScore_decada (~0.014)
4. Gross_por_Voto (~0.010)

## 🐛 Solução de Problemas

### Problemas Comuns

#### 1. Erro de Importação de Bibliotecas
```bash
# Reinstalar biblioteca específica
pip install --upgrade <nome-da-biblioteca>
```

#### 2. Jupyter não Inicia
```bash
# Verificar se está no ambiente virtual
.\venv\Scripts\activate

# Reinstalar Jupyter
pip install --upgrade jupyter
```

#### 3. Arquivo de Dados não Encontrado
- Verificar se o arquivo `desafio_indicium_imdb.csv` está na pasta `data/`
- Baixar novamente se necessário

#### 4. Erro de Memória
- Fechar outros programas
- Reiniciar o kernel do Jupyter
- Executar células individualmente

### Logs e Debugging
- Logs do CatBoost estão em `catboost_info/`
- Use `print()` statements para debug
- Verifique versões das bibliotecas: `pip list`

## 📝 Documentação Adicional

### Relatório Completo
O arquivo `relatorio_eda_analises.md` contém:
- Análise detalhada de cada etapa
- Interpretação dos resultados
- Visualizações e insights
- Recomendações para melhorias

### Notebook
O arquivo `LH_CD_LUCAS.ipynb` contém:
- Código completo comentado
- Visualizações interativas
- Análises passo a passo
- Resultados de modelagem

## 🤝 Contribuições

Para contribuir com o projeto:
1. Fork o repositório
2. Crie uma branch (`git checkout -b feature/nova-feature`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto foi desenvolvido para o Desafio Indicium de Ciência de Dados.

## 👨‍💻 Autor

**Lucas**
- Projeto: Desafio Indicium - Análise IMDb
- Data: Setembro 2025

## 📞 Suporte

Para dúvidas ou problemas:
1. Verifique a seção de Solução de Problemas
2. Consulte o relatório completo
3. Revise os comentários no notebook

---

**Nota**: Este projeto utiliza dados do IMDb para fins educacionais e de análise. Certifique-se de que tem as dependências corretas instaladas antes de executar o código.
