# Projeto Final - Análise de Dados de Carros Usados

API em Flask que utiliza Machine Learning (Regressão Linear) para prever o preço de carros usados com base em características como ano, quilometragem, motor e número de revisões.

## 📋 Sobre o Projeto

Este projeto realiza a leitura de um dataset de carros usados, treina um modelo de regressão linear com o **scikit-learn** e expõe uma API REST para consultar previsões de preço em tempo real.

## 🔗 Links

- **Site:** [godoymultimarcas.lovable.app](https://godoymultimarcas.lovable.app)
- **API:** _(https://projeto-final-analise-dados-mjzh.onrender.com)]_

## 🚀 Tecnologias Utilizadas

- **Python 3**
- **Flask** – framework web para criação da API
- **Flask-CORS** – habilita requisições de diferentes origens
- **Pandas** – manipulação e leitura dos dados
- **Scikit-learn** – treinamento do modelo de Regressão Linear
- **NumPy / SciPy** – suporte matemático e científico
- **Gunicorn** – servidor WSGI para produção

## 📁 Estrutura do Projeto

```
projeto-final-analise-dados/
├── app.py                     # API Flask principal
├── dataset_carros_usados.csv  # Base de dados usada no treinamento
├── requirements.txt           # Dependências do projeto
└── .gitignore
```

## ⚙️ Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/godoyeduardo135/projeto-final-analise-dados.git
   cd projeto-final-analise-dados
   ```

2. Crie e ative um ambiente virtual:
   ```bash
   python -m venv .venv
   source .venv/bin/activate   # Linux/Mac
   .venv\Scripts\activate      # Windows
   ```

3. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

## ▶️ Como Executar

```bash
python app.py
```

A API ficará disponível em `http://0.0.0.0:8000`.

## 🔌 Endpoints da API

### `GET /`
Verifica se a API está online.

**Resposta:**
```json
{
  "Resposta": "API online, Flask rodando corretamente"
}
```

### `POST /prever`
Recebe os dados de um carro e retorna o preço previsto pelo modelo.

**Corpo da requisição (JSON):**
```json
{
  "ano": 2018,
  "quilometragem": 45000,
  "motor": 1.6,
  "num_revisoes": 5
}
```

**Resposta de sucesso:**
```json
{
  "preco": 52340.75
}
```

**Resposta de erro:**
```json
{
  "erro": "Erro: <detalhe do erro>"
}
```

## 🧠 Sobre o Modelo

O modelo utiliza **Regressão Linear** (`LinearRegression` do scikit-learn), treinado com as seguintes variáveis de entrada (features):

- `ano`
- `quilometragem`
- `motor`
- `num_revisoes`

E como variável alvo (target):

- `preco`

## 📌 Observações

- O treinamento do modelo ocorre em memória, no momento em que a API é iniciada.
- O arquivo `dataset_carros_usados.csv` precisa estar presente na raiz do projeto para que a aplicação funcione corretamente.

## 👤 Autor

**Eduardo Godoy**
[GitHub - godoyeduardo135](https://github.com/godoyeduardo135)

**Eduardo Godoy**
[Linkedin - Eduardo Godoy](https://www.linkedin.com/in/eduardo-godoy-b73615272/)

## 🪪 Licença

Este repositório é de uso educacional, desenvolvido no contexto do curso de Fundamentos de IA e Análise de Dados.
