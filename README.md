# Google Drive Dashboard

## 📌 Visão Geral

**Objetivo**: Criar uma solução que permita manipular e monitorar arquivos no **Google Drive**, organizando-os em pastas e atualizando um **painel de controle** em tempo real com informações sobre esses arquivos. O painel de controle será um **Google Sheet** que será automaticamente atualizado sempre que houver alterações nos arquivos ou pastas.

Este projeto integra a **Google Drive API** para manipulação de arquivos no Drive e a **Google Sheets API** para visualização dos dados em um painel interativo (Google Sheets). A solução oferece automação, organização e acompanhamento em tempo real dos documentos.

---

## 🎯 Objetivos do Projeto

✔ **Carregar e organizar arquivos** no Google Drive, começando pela pasta principal que contém várias subpastas.  
✔ **Processar os dados** dos arquivos, extraindo metadados como **nome, data de modificação, ID, pasta**.  
✔ **Atualizar um painel no Google Sheets** com informações sobre os arquivos de forma estruturada.  
✔ **Automatizar o processo de sincronização** entre o Google Drive e o Google Sheets.  
✔ **Organizar e mover arquivos** de forma programática entre pastas dentro do Google Drive.

---

## 🛠️ Tecnologias Utilizadas  

| Tecnologia | Descrição |
|------------|--------------------------------|
| **Python** | Linguagem principal do projeto |
| **Google Drive API** | API para interação programática com o Google Drive |
| **Google Sheets API** | API para criação e atualização de planilhas Google |
| **gspread** | Biblioteca para facilitar o manuseio de Google Sheets em Python |
| **Google OAuth 2.0** | Protocolo de autenticação utilizado para garantir acesso seguro às APIs do Google |
| **requests** | Biblioteca para realizar requisições HTTP para APIs externas (caso necessário) |

---



---

---
---
---
---
---


## 📁 Estrutura do Projeto - Google Drive Dashboard

````md
📂 google-drive-dashboard  
├── 📂 src                         # Código-fonte do projeto
│   ├── 📜 __init__.py               # Arquivo de inicialização do pacote
│   ├── 📜 drive_api.py             # Interação com a API do Google Drive (listagem, movimentação, etc.)
│   ├── 📜 sheets_api.py            # Interação com a API do Google Sheets (para atualizar dashboard)
│   ├── 📜 authentication.py        # Gerenciamento da autenticação OAuth 2.0
│   ├── 📜 config.py                # Configurações do projeto (IDs de pasta, credenciais, etc.)
│   └── 📜 main.py                  # Arquivo principal para rodar o programa
│
├── 📂 credentials/                 # Pasta para armazenar credenciais
│   ├── 📄 credentials.json         # Arquivo de credenciais do OAuth 2.0 (obtido no Google Cloud Console)
│   └── 📄 token.pickle             # Arquivo de token gerado pela autenticação
│
├── 📂 logs/                        # Logs do processo de execução
│   └── 📄 app.log                  # Logs de atividades (opcional, para depuração)
│
├── 📂 venv                         # Ambiente virtual
│   └── 📂 ...                      # Arquivos do ambiente virtual (não precisam ser versionados)
│
├── 📄 requirements.txt             # Dependências do Python (bibliotecas necessárias)
├── 📄 README.md                    # Documentação do projeto
└── .gitignore                      # Ignorar arquivos não necessários para controle de versão
````

## 📊 Fluxo do Projeto

### 1. **Configuração do Google Cloud**
- Criação de um novo projeto no **Google Cloud Console**.
- Ativação das **Google Drive API** e **Google Sheets API**.
- Criação de credenciais OAuth 2.0 para autenticação.

### 2. **Autenticação**
- O script Python usará o **OAuth 2.0** para autenticar o acesso às APIs do Google.
- Após a autenticação, um **token de acesso** será gerado e armazenado localmente para uso futuro.

### 3. **Interação com a Google Drive API**
- O script Python usará a **Google Drive API** para listar, mover e organizar arquivos dentro da **pasta principal** e suas **subpastas**.
- A API será usada para coletar informações sobre os arquivos (nome, ID, data de modificação).

### 4. **Atualização do Google Sheets**
- A biblioteca **gspread** será usada para atualizar automaticamente as informações no Google Sheets com os dados coletados da **Google Drive API**.
- Cada vez que um arquivo for listado ou movido, as informações serão registradas no **painel de controle** (Google Sheets).

### 5. **Automação e Manutenção**
- O script Python será executado periodicamente para garantir que o painel de controle seja mantido atualizado com informações mais recentes.
- O Google Sheets servirá como uma **visualização em tempo real** para os documentos do Google Drive.

---

## 🚀 Uso do Projeto

### 📌 Pré-requisitos
Antes de começar, instale as bibliotecas necessárias:
```bash
pip install google-api-python-client google-auth-httplib2 google-auth-oauthlib gspread

````
