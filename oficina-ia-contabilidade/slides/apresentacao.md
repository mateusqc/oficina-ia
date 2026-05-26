# IA Aplicada à Contabilidade

Oficina prática

**Ideia central:** transformar mensagens e documentos em dados acionáveis.

Visual sugerido: mesa de escritório contábil com notebook, planilha e documentos fiscais.

---

# Antes de começar

**Pergunta no Mentimeter**

Onde você mais perde tempo hoje?

- organizar documentos
- responder clientes
- conferir informações
- alimentar planilhas
- entender pendências

Visual sugerido: nuvem de palavras ao vivo.

---

# O que é IA Generativa

IA que cria respostas a partir de contexto.

Exemplos:

- resumir um e-mail
- explicar uma dúvida fiscal
- extrair dados de uma nota
- escrever uma mensagem para cliente

Visual sugerido: entrada em linguagem natural virando saída organizada.

---

# O que é um LLM

LLM é um modelo que entende e gera texto.

Ele não "sabe contabilidade" sozinho.

Ele precisa de:

- contexto
- instrução
- exemplo
- formato de saída

Visual sugerido: quatro blocos formando um prompt.

---

# Onde IA entra na contabilidade

IA ajuda antes da operação repetitiva.

- ler mensagens
- identificar intenção
- organizar documentos
- sugerir ação
- gerar rascunhos

O ERP continua sendo o sistema principal.

Visual sugerido: e-mail/documento entrando, dados saindo para planilha/ERP.

---

# Conceito central

**LLMs transformam linguagem natural e documentos em dados estruturados acionáveis.**

Exemplo:

"Segue XML de abril, pode confirmar?"

vira:

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

Objetivo: mostrar a primeira conexão entre n8n e modelo local.

Visual sugerido: três blocos conectados.

---

# Prompt engineering

Um bom prompt simples tem:

- papel
- contexto
- tarefa
- formato

Exemplo:

> Você é um assistente contábil. Explique em linguagem simples para um cliente iniciante.

Pouco texto. Instrução clara.

---

# Fluxo 01

## Triagem de e-mails

Webhook simulando e-mail  
→ LLM classifica intenção  
→ Switch roteia  
→ Google Sheets registra

Tipos:

- envio_xml
- dúvida_fiscal
- cobrança
- pendência_documental
- solicitação_folha

Visual sugerido: caixa de entrada virando filas de atendimento.

---

# Fluxo 01: exemplo

Entrada:

> "Segue o extrato de abril. As notas de entrada envio depois."

Saída:

```json
{
  "tipo": "pendencia_documental",
  "cliente": "Lima Distribuidora",
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

Visual sugerido: PDF de nota fiscal virando uma linha de planilha.

---

# Fluxo 02: ideia principal

Não é OCR avançado.

É demonstração de interpretação.

Texto extraído:

> Fornecedor: Costa Serviços Fictícios Ltda  
> Valor total: R$ 1.850,00

Resultado:

```json
{
  "categoria": "servicos_tomados"
}
```

---

# Fluxo 03

## Comunicação de pendências

Pendência  
→ LLM gera mensagem  
→ Google Sheets registra

Exemplo:

```json
{
  "cliente": "XPTO LTDA",
  "pendencia": "XML da competência 05/2026 não enviado"
}
```

Visual sugerido: pendência virando mensagem profissional.

---

# Fluxo 03: mensagem gerada

Tom esperado:

- profissional
- claro
- cordial
- direto

Exemplo:

> Olá, XPTO LTDA. Para concluirmos o fechamento da competência 05/2026, precisamos do XML pendente. Poderia nos enviar, por favor?

Não envia e-mail real. Apenas gera o rascunho.

---

# ERP e Domínio

A IA não substitui o ERP.

Ela atua como camada operacional:

- interpreta mensagens
- organiza documentos
- prepara dados
- sugere encaminhamentos

Depois disso, o ERP continua como fonte oficial.

Visual sugerido: IA antes do ERP, preparando informação.

---

# Possibilidades futuras

Depois da oficina, dá para evoluir para:

- checklist automático de fechamento
- leitura de mais documentos
- priorização de atendimento
- respostas padronizadas
- integração controlada com sistemas internos

Sempre começando pequeno.

---

# Encerramento

O que vimos:

- IA conversando
- IA classificando intenção
- IA lendo documento
- IA gerando comunicação
- n8n conectando tudo

Mensagem final:

**IA automatiza interpretação, organização e tomada inicial de decisão.**

