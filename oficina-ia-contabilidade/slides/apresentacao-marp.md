---
marp: true
theme: default
paginate: true
size: 16:9
style: |
  section {
    font-family: Arial, Helvetica, sans-serif;
    color: #172033;
    background: #f7f8fb;
    padding: 56px;
  }
  h1 {
    color: #0f4c81;
    font-size: 44px;
    margin-bottom: 18px;
  }
  h2 {
    color: #2f5f73;
    font-size: 28px;
    margin-top: 0;
  }
  p, li {
    font-size: 26px;
    line-height: 1.35;
  }
  code {
    font-size: 20px;
  }
  pre {
    background: #ffffff;
    border: 1px solid #d9e1ec;
    border-radius: 8px;
    padding: 18px;
  }
  blockquote {
    border-left: 6px solid #0f4c81;
    color: #25324a;
    padding-left: 18px;
  }
  .small {
    font-size: 20px;
    color: #5b6678;
  }
---

<!-- _class: lead -->

# IA Aplicada à Contabilidade

## Oficina prática

**Transformar mensagens e documentos em dados acionáveis.**

---

# Antes de começar

## Pesquisa Mentimeter

Onde você mais perde tempo hoje?

- organizar documentos
- responder clientes
- conferir informações
- alimentar planilhas
- entender pendências

---

# O que é IA Generativa

IA que cria respostas a partir de contexto.

Exemplos:

- resumir um e-mail
- explicar uma dúvida fiscal
- extrair dados de uma nota
- escrever uma mensagem para cliente

---

# O que é um LLM

LLM é um modelo que entende e gera texto.

Ele precisa de:

- contexto
- instrução
- exemplo
- formato de saída

---

# Onde IA entra na contabilidade

IA ajuda antes da operação repetitiva.

- lê mensagens
- identifica intenção
- organiza documentos
- sugere ação
- gera rascunhos

**O ERP continua sendo o sistema principal.**

---

# Conceito central

**LLMs transformam linguagem natural e documentos em dados estruturados acionáveis.**

```json
{
  "tipo": "envio_xml",
  "competencia": "2026-04",
  "acao": "registrar recebimento"
}
```

---

# Fluxo 00

## IA conversando

Webhook → LM Studio → resposta

Pergunta exemplo:

> Explique o que é lucro presumido.

Objetivo: primeira conexão entre n8n e modelo local.

---

# Prompt engineering

Um prompt simples tem:

- papel
- contexto
- tarefa
- formato

Exemplo:

> Você é um assistente contábil. Explique em linguagem simples para um cliente iniciante.

---

# Fluxo 01

## Triagem de e-mails

Webhook simulando e-mail  
→ LLM classifica intenção  
→ Switch roteia  
→ Google Sheets registra

Tipos:

`envio_xml` `duvida_fiscal` `cobranca` `pendencia_documental` `solicitacao_folha`

---

# Fluxo 01: exemplo

Entrada:

> "Segue o extrato de abril. As notas de entrada envio depois."

Saída:

```json
{
  "tipo": "pendencia_documental",
  "competencia": "2026-04",
  "urgencia": "normal",
  "acao": "cobrar notas de entrada"
}
```

---

# Fluxo 02

## Leitura de nota fiscal PDF

Upload PDF  
→ extração de texto  
→ LLM interpreta  
→ Google Sheets registra

Campos:

- fornecedor
- CNPJ
- valor total
- competência
- categoria

---

# Fluxo 02: ideia principal

Não é OCR avançado.

É demonstração de interpretação.

```json
{
  "fornecedor": "Costa Serviços Fictícios Ltda",
  "valor_total": "1850.00",
  "categoria": "servicos_tomados"
}
```

---

# Fluxo 03

## Comunicação de pendências

Pendência  
→ LLM gera mensagem  
→ Google Sheets registra

```json
{
  "cliente": "XPTO LTDA",
  "pendencia": "XML da competência 05/2026 não enviado"
}
```

---

# Fluxo 03: mensagem gerada

Tom esperado:

- profissional
- claro
- cordial
- direto

> Para concluirmos o fechamento da competência 05/2026, precisamos do XML pendente. Poderia nos enviar, por favor?

---

# ERP e Domínio

A IA não substitui o ERP.

Ela atua como camada operacional:

- interpreta mensagens
- organiza documentos
- prepara dados
- sugere encaminhamentos

Depois disso, o ERP continua como fonte oficial.

---

# Possibilidades futuras

Evoluções possíveis:

- checklist automático de fechamento
- leitura de mais documentos
- priorização de atendimento
- respostas padronizadas
- integração controlada com sistemas internos

**Sempre começando pequeno.**

---

# Encerramento

Hoje vimos IA:

- conversando
- classificando intenção
- lendo documento
- gerando comunicação
- conectada pelo n8n

**IA automatiza interpretação, organização e tomada inicial de decisão.**

