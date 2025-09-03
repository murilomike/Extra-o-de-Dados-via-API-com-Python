# 📡 Extração de Dados da Bored API com Python

Este projeto tem como objetivo demonstrar o processo de extração de dados de uma API pública — a [Bored API](https://bored-api.appbrewery.com/) — utilizando Python no ambiente do Google Colab. A abordagem segue os princípios de ETL (Extract, Transform, Load), com foco na coleta de atividades sugeridas pela API e posterior organização em formato tabular.

---

## 🧪 Etapas do Procedimento

### 1. Importação de Bibliotecas

O projeto inicia com a importação das bibliotecas necessárias para realizar requisições HTTP, manipular dados tabulares e controlar o tempo entre tentativas em caso de erro.

### 2. Configuração de Parâmetros

São definidos parâmetros como:
- A URL da API (endpoint aleatório ou filtrado)
- Número de requisições desejadas
- Número máximo de tentativas por requisição
- Tempo limite para resposta

Esses parâmetros garantem controle sobre a coleta e ajudam a lidar com possíveis falhas de conexão.

### 3. Requisição à API

Foi criada uma função que realiza a chamada à API utilizando `requests.get()`, com tratamento de exceções para garantir robustez. Em caso de falha, o sistema tenta novamente até o limite definido.

### 4. Coleta de Dados

A função de requisição é executada em um loop, coletando múltiplas atividades e armazenando os resultados em uma lista. Cada item retornado pela API é um dicionário com informações como tipo de atividade, número de participantes, preço e acessibilidade.

### 5. Transformação dos Dados

Os dados coletados são convertidos para um DataFrame com `pandas`. São selecionadas apenas as colunas relevantes, renomeadas para português, e duplicatas são removidas para garantir qualidade.

### 6. Salvamento em CSV

O DataFrame final é exportado para um arquivo `.csv`, permitindo que os dados sejam utilizados em outras ferramentas ou visualizados posteriormente.

---

## 🔍 Outras Extrações

Além da coleta aleatória, o projeto também demonstra:
- Extração por **chave específica** (`/activity/3943506`)
- Extração por **filtro de tipo** (`/filter?type=education`)

Essas abordagens permitem maior controle sobre os dados retornados pela API.

---

## 📁 Resultado

O resultado final é um conjunto de arquivos `.csv` contendo atividades organizadas e prontos para análise, visualização ou integração com outros sistemas.

---

