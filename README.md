
# 📈 Previsão de Aderência a Investimentos em Campanhas de Marketing

Este projeto tem como objetivo prever a **aderência de clientes** a um investimento oferecido em campanhas de marketing de um banco, utilizando algoritmos de **Machine Learning** e técnicas de **análise de dados**.

A partir de um conjunto de dados realista contendo informações demográficas e financeiras dos clientes, o modelo é capaz de identificar padrões que indicam a probabilidade de um cliente aderir ou não à proposta.

---

## 🧠 Técnicas Utilizadas

- Análise exploratória de dados (EDA)
- Pré-processamento e transformação dos dados
- Codificação de variáveis categóricas com **OneHotEncoder**
- Normalização com **MinMaxScaler**
- Treinamento de modelos com:
  - DummyClassifier (baseline)
  - Decision Tree Classifier
  - K-Nearest Neighbors (KNN)
- Avaliação de acurácia dos modelos
- Salvamento dos modelos com **pickle**
- Testes de predição com novos dados

---

## 🗂️ Estrutura do Projeto

```
marketing-investimento/
│
├── data/
│   └── marketing_investimento.csv     # Dataset original
│
├── modelos/
│   ├── modelo_onehotenc.pkl           # OneHotEncoder salvo
│   └── modelo_tree.pkl                # Modelo final (Árvore de Decisão)
│
├── notebooks/
│   └── marketing_modelo.ipynb         # Jupyter Notebook com todo o código
│
├── README.md                          # Este arquivo
└── requirements.txt                   # Bibliotecas necessárias
```

---

## 📊 Dataset

O dataset pode ser acessado diretamente por este link:

📁 [`marketing_investimento.csv`](https://raw.githubusercontent.com/TheGabrielVieira/classificacao-dados-machine-learning/refs/heads/main/data/marketing_investimento.csv)

Cada linha representa um cliente e contém informações como:

- Idade
- Estado civil
- Escolaridade
- Inadimplência
- Saldo bancário
- Se fez ou não empréstimo
- Tempo do último contato
- Número de contatos realizados
- Aderência ao investimento (variável alvo)

---

## ⚙️ Como executar localmente

1. **Clone este repositório:**

```bash
git clone https://github.com/seu-usuario/marketing-investimento.git
cd marketing-investimento
```

2. **Crie e ative um ambiente virtual (opcional, mas recomendado):**

```bash
python -m venv venv
source venv/bin/activate      # Linux/macOS
venv\Scripts\activate.bat     # Windows
```

3. **Instale as dependências:**

```bash
pip install -r requirements.txt
```

4. **Execute o Jupyter Notebook:**

```bash
jupyter notebook
```

5. **Abra o arquivo `notebooks/marketing_modelo.ipynb` e execute as células.**

---

## 🧪 Teste com novo cliente

Você pode testar o modelo final com novos dados usando o código abaixo:

```python
import pandas as pd
import pickle

novo_dado = pd.DataFrame({
    'idade': [45],
    'estado_civil': ['solteiro (a)'],
    'escolaridade': ['superior'],
    'inadimplencia': ['nao'],
    'saldo': [23040],
    'fez_emprestimo': ['nao'],
    'tempo_ult_contato': [800],
    'numero_contatos': [4]
})

encoder = pd.read_pickle('modelo_onehotenc.pkl')
modelo = pd.read_pickle('modelo_tree.pkl')

novo_dado_transformado = encoder.transform(novo_dado)
predicao = modelo.predict(novo_dado_transformado)

print(f'Predição: {predicao}')  # 0 = não aderiu, 1 = aderiu
```

---

## 🛠️ Tecnologias e Bibliotecas

- Python 3.10+
- pandas
- plotly
- matplotlib
- scikit-learn
- pickle

---

## 📌 Requisitos

- Python instalado
- Jupyter Notebook (opcional para visualização interativa)

---

## 📚 Inspiração

Este projeto foi desenvolvido como prática de classificação supervisionada e manipulação de dados, servindo como base para aplicações em bancos, marketing e crédito.

---

## 📬 Contato

Desenvolvido por **Gabriel Vieira**  
[GitHub](https://github.com/TheGabrielVieira)
