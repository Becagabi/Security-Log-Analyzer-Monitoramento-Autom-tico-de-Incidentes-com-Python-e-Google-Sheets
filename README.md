# Security Log Analyzer: Automação de Monitoramento de Incidentes com Python e Google Sheets 🐍📊
 
Este projeto demonstra uma solução de **Análise de Logs de Segurança (SIEM básico)** totalmente automatizada. Ele utiliza o Python para processar logs de acesso, identificar padrões de ataque, enriquecer os dados com geolocalização e exportar o resultado final para um dashboard visual no Google Sheets.
 
O objetivo é transformar logs brutos em informações acionáveis para uma triagem e Resposta a Incidentes (IR) mais rápida e eficiente, ideal para projetos que simulam um ambiente de **SOC (Security Operations Center)**.
 
## ⚙️ Tecnologias Utilizadas
 
* **Linguagem:** Python

* **Análise de Dados:** `pandas`

* **Requisições Web:** `requests` (para consulta à API de geolocalização `ipinfo.io`)

* **Integração com Google:** `gspread`, `oauth2client`

* **Ambiente:** Google Colab / Jupyter Notebook

* **Visualização:** Google Sheets (Dashboard)
 
## 💡 Principais Funcionalidades
 
1.  **Ingestão de Dados:** Leitura e tratamento de um arquivo CSV de logs de acesso (Dataset simulado de Honeypot do Kaggle).

2.  **Detecção de Ameaças (Payload Analysis):** Implementação de uma função avançada (`detectar_payload_improved`) que utiliza Expressões Regulares (`re`) e heurísticas para classificar payloads e atribuir um **score de risco**, identificando:

    * Injeções (`sql_injection`, `xss`, `command_injection`).

    * Sinais de Scanners e Probes (`scanner_signs`).

    * Tráfego binário (`suspicious_tls_clienthello`).

3.  **Enriquecimento de Dados:** Consulta à API de geolocalização (`ipinfo.io`) para adicionar o país de origem a cada IP suspeito.

4.  **Agregação de Incidentes:** Contagem e consolidação das tentativas de ataque (falhas e sucessos) por IP.

5.  **Exportação Automatizada (Geração do Dashboard):** Uso do `gspread` para enviar o Dataframe processado para diversas abas de uma planilha no Google Sheets, mantendo o Dashboard de Monitoramento sempre atualizado para visualização instantânea (conforme o [exemplo de dashboard](LINK-PARA-A-IMAGEM-OU-DASHBOARD-PUBLICO-AQUI)).
 
## 🚀 Como Usar e Replicar
 
### 1. Pré-requisitos

Certifique-se de ter o Python e as seguintes bibliotecas instaladas:
 
```bash

pip install pandas requests gspread oauth2client
 
