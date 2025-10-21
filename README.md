Security Log Analyzer: Automação de Monitoramento de Incidentes com Python e Google Sheets 🐍📊
 
Visão Geral do Projeto
 
Este projeto demonstra uma solução de Análise de Logs de Segurança (Security Information and Event Management - SIEM básico) totalmente automatizada. Ele utiliza o Python para processar logs de acesso, identificar padrões de ataque, enriquecer os dados com geolocalização e exportar o resultado final para um dashboard visual no Google Sheets.
O objetivo é transformar logs brutos em informações acionáveis para uma triagem e Resposta a Incidentes (IR) mais rápida e eficiente.
 
⚙️ Tecnologias Utilizadas
 
Linguagem: Python
Análise de Dados: pandas
Requisições Web: requests (para consultar a API de geolocalização ipinfo.io)
Integração com Google: gspread, oauth2client
Ambiente: Google Colab / Jupyter Notebook
Visualização: Google Sheets (Dashboard)
 
💡 Principais Funcionalidades
 
Ingestão de Dados: Leitura de um arquivo CSV de logs de acesso (Dataset simulado de Honeypot).
Detecção de Ameaças: Implementação de uma função avançada (detectar_payload_improved) que utiliza Expressões Regulares (re) para classificar payloads em categorias de ataque, como:
sql_injection
xss
command_injection
path_traversal
scanner_signs (detecção de ferramentas como Nmap, Masscan, etc.)
Enriquecimento de Dados: Consulta à API de geolocalização (ipinfo.io) para adicionar o país de origem a cada IP suspeito.
Agregação de Incidentes: Contagem de tentativas de ataque (falhas e sucessos) por IP.
Exportação Automatizada: Utilização do gspread para enviar o Dataframe processado para diversas abas de uma planilha no Google Sheets, mantendo o Dashboard de Monitoramento sempre atualizado.
 
💾 Estrutura do Repositório
 
projeto.ipynb: O Notebook Python principal que contém todo o código de ETL, análise e integração com o Google Sheets.
london.csv: O arquivo de logs (dataset fictício de entrada). (Nota: Este dataset é baseado em logs públicos, como os encontrados em plataformas como Kaggle).
chave_google.json: Arquivo de credenciais da Conta de Serviço do Google Cloud, necessário para a integração com o gspread. (Deve ser substituído pelo seu próprio arquivo de credenciais e NÃO deve ser enviado ao repositório público por questões de segurança).
[Link do Dashboard - Opcional]: Link público para a cópia do Dashboard no Google Sheets (para visualização do resultado final).
 
🛠️ Como Usar
 
Clone o Repositório:
Bash
 
git clone https://github.com/SeuUsuario/Security-Log-Analyzer.git
Configurar Credenciais do Google Sheets:
Crie uma conta de serviço no Google Cloud.
Baixe o arquivo JSON da chave.
Renomeie o arquivo para chave_google.json e coloque-o na mesma pasta do Notebook.
Compartilhe a sua planilha Google Sheets (Monitoramento Log) com o email da sua conta de serviço.
Instalar Dependências:
Bash
 
pip install pandas requests gspread oauth2client
Executar o Notebook: Abra e execute o projeto.ipynb no seu ambiente preferido (Jupyter ou Google Colab).
