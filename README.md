# 🌍 Monitor de Temperatura por Coordenadas (Google Sheets + Open-Meteo API)

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) 
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) 
![Open-Meteo](https://img.shields.io/badge/API-Open--Meteo-blue?style=for-the-badge) 

Este projeto automatiza a coleta de dados de temperatura em tempo real para múltiplos locais geográficos cadastrados em uma planilha do Google Sheets. Ele lê a lista de locais, latitude e longitude diretamente da planilha e consulta a API pública **Open-Meteo** para obter o clima atual de cada ponto.

## 🚀 Funcionalidades

- **Integração com Google Sheets:** Consome dados de localização de forma dinâmica via exportação CSV direta.
- **Consulta de Clima em Tempo Real:** Conecta-se à API Open-Meteo para obter a temperatura atual do ar (`temperature_2m`).
- **Automação Pronta para Loops:** Estrutura em loops que permite monitorar quantos locais forem necessários de forma rápida e eficiente.

## 🛠️ Tecnologias Utilizadas

*   [Python 3](https://www.python.org/)
*   [Pandas](https://pandas.pydata.org/) (Manipulação e leitura de dados estruturados)
*   [Requests](https://requests.readthedocs.io/) (Requisições HTTP para a API)
*   [Open-Meteo API](https://open-meteo.com/) (Provedor gratuito de dados meteorológicos)

---

## 📂 Estrutura de Dados (Planilha de Origem)

A planilha lida pelo script deve possuir as seguintes colunas obrigatórias:

| Carimbo de data/hora | Nome do local | Latitude | Longitude |
| :--- | :--- | :--- | :--- |
| `18/11/2026 14:50:38` | Exemplo de Local | `-24.70` | `-47.55` |

*A planilha utilizada originalmente neste projeto pode ser acessada [neste link](https://docs.google.com/spreadsheets/d/1PCMZwYxTT4GFwCqVGuCkBVvK1kae9Biw1g7-urZjFiQ/edit?usp=sharing).*

---

## 🔧 Como Executar o Projeto

### 1. Pré-requisitos

Certifique-se de ter o Python instalado e instale as dependências necessárias:

```bash
pip install pandas requests
2. Execução
Basta clonar o repositório e executar o script principal:

# Clonar o repositório
git clone https://github.com/seu-usuario/seu-repositorio.git

# Entrar na pasta
cd seu-repositorio

# Executar o script
python main.py
📊 Exemplo de Saída (Output)
Ao executar o script para cada local cadastrado, você receberá um retorno estruturado em JSON contendo os dados meteorológicos atuais:

{
  "latitude": -22.952549,
  "longitude": -47.066803,
  "elevation": 684.0,
  "current_units": {
    "time": "iso8601",
    "temperature_2m": "°C"
  },
  "current": {
    "time": "2026-11-18T22:45",
    "temperature_2m": 21.3
  }
}
