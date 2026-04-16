# Base de Conhecimento

## Dados Utilizados

Os dados utilizados foram extraidos da API do portal Bolsai e do Banco Central, os arquivos .csv e .json da CVM e arquivos extraidos de portais de noticias

> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Não utilizei eles, peguei dados da API do portal Bolsai e do Banco Central, e os arquivos .csv e .json da CVM e arquivos extraidos de portais de noticias

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.
Dados via código e via prompt
```python
import requests
import json
import pandas as pd 
#-----------------------------------------------
#Para os Arquivos .csv:
#Arquivo = pd.read_csv("Caminho do Arquivo")
#-----------------------------------------------
#Para os Arquivos .json:
#with open("caminho do arquivo", "r", encoding="utf-8") as f:
#        return pd.DataFrame(json.load(f))
#-----------------------------------------------
#Para APIs (exemplo para consulta):
#API_KEY = "Chave da API"
#Exemplo função para consultar uma Ação
#def get_fundamentals(ticker): 
#    url = f"https://api.usebolsai.com/api/v1/fundamentals/{ticker}"

#    headers = {
#        "X-API-Key": API_KEY
#    }

#    response = requests.get(url, headers=headers)

#    if response.status_code == 200:
#        return response.json()
#    else:
#        print(f"Erro {response.status_code} para {ticker}")
#        return None
```

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

Os dados podem ser inserirdos no prompt, ou consultados via arquivos (.csv e .json) ou APIs

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

O exemplo abaixo demonstra os dados extraidos das APIS e dos arquivos .csv e .json, alem dos arquivos extraidos de portais de noticias
```python
Dados de Ações e FIIs:
Dados de Histórico da SELIC:
Dados de Histórico do IPCA:
Dados de Histórico de IGPM:
Dados das Notícias Extraidas:
```
