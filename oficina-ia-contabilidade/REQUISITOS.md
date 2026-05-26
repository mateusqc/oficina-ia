# Requisitos do Projeto da Oficina

## Objetivo

Gerar todos os artefatos necessários para execução local de uma oficina prática de IA aplicada à contabilidade.

---

# Artefatos obrigatórios

## Infraestrutura

### docker/docker-compose.yaml

Deve subir:
- n8n;
- volumes persistentes;
- configurações mínimas necessárias.

NÃO incluir:
- bancos complexos;
- dependências desnecessárias.

LM Studio será executado manualmente no host.

---

# README.md

Deve conter:
- visão geral;
- pré-requisitos;
- como iniciar a infraestrutura;
- como acessar n8n;
- como configurar Google Sheets;
- como configurar credenciais;
- roteiro resumido da oficina;
- troubleshooting simples.

---

# Diretório `dados/`

Deve conter:

## PDFs de exemplo
Notas fiscais fictícias.

## XMLs fictícios
NF-es simplificadas.

## Dados CSV
Exemplos de:
- pendências;
- classificações;
- e-mails simulados.

## Exemplos realistas

Os dados devem:
- simular rotina contábil real;
- conter nomes fictícios;
- conter CNPJs fictícios;
- parecer plausíveis.

---

# Diretório `fluxos/`

Deve conter:

## fluxo-00-agente-simples.json

Workflow:
- input texto;
- chamada LLM;
- resposta simples.

---

## fluxo-01-triagem-emails.json

Workflow:
- webhook simulando e-mail;
- classificação via LLM;
- structured output;
- switch;
- gravação Google Sheets.

---

## fluxo-02-extracao-nf-pdf.json

Workflow:
- upload PDF;
- extração texto;
- chamada LLM;
- structured output;
- gravação Google Sheets.

---

## fluxo-03-geracao-pendencias.json

Workflow reserva.

---

# Diretório `slides/`

## apresentacao.md

Conteúdo em markdown:
- utilizado posteriormente no Gamma;
- estruturado em seções;
- linguagem simples;
- pouco texto por slide.

---

## apresentacao-marp.md

Versão compatível com Marp.

---

# Diretório `docs/`

Deve conter:
- instruções auxiliares;
- prompts utilizados;
- schemas JSON;
- exemplos de requests/responses;
- troubleshooting.

---

# Requisitos técnicos

## n8n

- workflows simples;
- nodes bem nomeados;
- evitar lógica excessiva;
- evitar JavaScript complexo.

---

## LLM

API compatível com OpenAI.

Assumir:
- endpoint local;
- baixa latência;
- respostas curtas;
- structured output.

---

## Google Sheets

Usar:
- poucas abas;
- nomes claros;
- estrutura simples.

---

# Não fazer

- integrações reais com ERP;
- APIs do Domínio;
- OCR complexo;
- autenticações avançadas;
- pipelines complexos;
- agentes sofisticados;
- RAG.

---

# Critérios pedagógicos

A oficina deve ensinar:

1. O que é um LLM
2. Como prompts funcionam
3. Como IA interpreta intenção
4. Como IA interpreta documentos
5. Como IA gera dados estruturados
6. Como workflows automatizam processos

---

# Estilo esperado

- extremamente prático;
- visual;
- operacional;
- orientado à realidade de escritório contábil.
