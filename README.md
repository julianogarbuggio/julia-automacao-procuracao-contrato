# 🧠 Jul.IA – Automação de Procuração e Contrato de Consignado

Sistema automatizado para geração instantânea de **procurações** e **contratos de empréstimo consignado**, com inserção dinâmica de dados, preenchimento padronizado e exportação em **DOCX/PDF** totalmente formatados.

A solução foi criada para escritórios jurídicos que precisam de **velocidade**, **consistência** e **automação** em documentos recorrentes de mandato e contratação de empréstimo.

---

## ✅ Funcionalidades

### 🔎 Entrada e processamento de dados

- Formulário único com validação básica
- Captura de dados completos do cliente em formato de bloco ("Rótulo: valor")
- Quebra automática do endereço em:
  - Logradouro
  - Número
  - Complemento
  - Bairro
  - CEP
  - Cidade / Estado
- Normalização de campos como RG ("número - ESTADO: UF"), CPF, cidade e UF

### 📄 Geração de documentos

- Emissão automática de:
  - **Procuração**
  - **Contrato de Empréstimo Consignado**
- Templates em DOCX totalmente personalizáveis
- Preenchimento dinâmico via **docxtpl**
- Negrito automático no nome do cliente em todo o documento, preservando a fonte base
- Exportação em **DOCX** e **PDF**  
  - PDF via **docx2pdf** (quando disponível)  
  - Fallback via **LibreOffice (soffice — headless)**

### 🧮 Funcionalidades inteligentes

- Tratamento de acentos e caracteres especiais
- Ajuste automático de campos jurídicos padrão
- Arquivos nomeados com base no nome do cliente (ex.: `Maria_Silva_gerado.docx` / `.pdf`)

### 💼 Uso profissional

- Ideal para:
  - Escritórios de advocacia
  - Departamentos jurídicos
  - Automação de backoffice jurídico
- Pensado para integração futura com:
  - Bots de WhatsApp
  - Portais / formulários web
  - Outras instâncias da Jul.IA (Petições, Agenda, Procurações etc.)

---

## ⚙️ Tecnologias utilizadas

### Backend

- 🐍 **Python 3.11**
- ⚡ **FastAPI** (API + interface web)
- 📝 **docxtpl** + **python-docx** para manipulação de DOCX

### PDF

- 🖨️ **docx2pdf**
- 🖥️ **LibreOffice (soffice --headless)** como fallback de conversão

### Frontend

- 🌐 HTML + CSS + JavaScript Vanilla
- Layout enxuto em página única para uso diário no escritório

### Deploy

- 🚀 **Railway**, via Dockerfile simples

---

## 🌍 Endpoints principais

| Método | Rota           | Descrição                                     |
|-------|----------------|-----------------------------------------------|
| GET   | `/`            | Interface web principal                       |
| GET   | `/docx`        | Página dedicada para geração de DOCX          |
| GET   | `/pdf`         | Página dedicada para geração de PDF           |
| POST  | `/gerar-docx`  | Gera e retorna o DOCX com base no bloco dado  |
| POST  | `/gerar-pdf`   | Gera e retorna o PDF com base no bloco dado   |

---

## 🛠️ Como rodar localmente

```bash
git clone https://github.com/SEU-USUARIO/julia-automacao-procuracao-contrato.git
cd julia-automacao-procuracao-contrato

python -m venv .venv
# Windows
.venv\Scripts\activate
# Linux / macOS
# source .venv/bin/activate

pip install -r requirements.txt

uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

Depois é só acessar:

> http://127.0.0.1:8000

---

## ☁️ Deploy no Railway

Este projeto já está pronto para deploy via Docker:

1. Crie um novo projeto no Railway
2. Escolha **Deploy from GitHub Repo**
3. Selecione o repositório desta aplicação
4. O Railway irá:
   - Fazer o build da imagem Docker
   - Executar o comando padrão com `uvicorn app.main:app`

Nenhuma variável de ambiente é obrigatória.  
O sistema funciona **out-of-the-box**.

---

## 📝 Licença e direitos

© 2025 **Juliano Garbuggio - Advocacia & Consultoria**  
**Powered by Jul.IA – Inteligência Jurídica Automatizada**

---

## ❤️ Contribuição

Sugestões, melhorias e PRs são bem-vindos.  
Este repositório foi pensado para ser base de automações mais avançadas, incluindo integração com:

- Jul.IA Petições
- Jul.IA Agenda e Intimações
- Jul.IA Procurações (via web / WhatsApp)

---

## 📬 Contato

Para dúvidas, suporte ou parcerias:

- 📧 E-mail profissional: `juliano@garbuggio.adv.br` (ou o e-mail que preferir configurar)
- 📱 WhatsApp de atendimento integrado à Jul.IA

