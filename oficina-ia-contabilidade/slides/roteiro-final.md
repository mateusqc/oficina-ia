# IA Aplicada à Contabilidade

## LLMs, Prompts e Automação Inteligente com n8n

---

# Abertura Interativa

## Vamos usar o Mentimeter durante a oficina

Acesse:

```text id="2hxhl7"
www.menti.com
```

Digite o código exibido na tela.

---

# Transição

## O objetivo desta oficina

Mostrar como IA pode:

* entender linguagem;
* interpretar documentos;
* transformar texto em dados estruturados;
* automatizar processos contábeis reais.

---

# Sobre esta oficina

## Objetivo

Ao final desta oficina, você será capaz de:

* entender o que são LLMs;
* compreender o papel dos prompts;
* transformar texto em workflows automatizados;
* utilizar IA em processos contábeis reais;
* construir automações simples utilizando IA + n8n.

---

# O foco desta oficina NÃO é

* teoria pesada;
* matemática;
* machine learning acadêmico;
* construir modelos de IA.

---

# O foco desta oficina É

* aplicações práticas;
* produtividade;
* automação;
* workflows inteligentes;
* integração com processos contábeis.

---

# O problema dos sistemas atuais

Hoje os sistemas:

* armazenam dados;
* executam regras;
* processam informações estruturadas.

Mas normalmente NÃO conseguem:

* entender linguagem;
* interpretar contexto;
* analisar documentos;
* tomar decisões simples;
* organizar informação não estruturada.

---

# O caos operacional contábil

No dia a dia temos:

* dezenas de e-mails;
* XMLs;
* SPED;
* PDFs;
* mensagens;
* notas fiscais;
* comprovantes;
* contratos;
* solicitações repetitivas.

Tudo isso precisa ser:

* lido;
* interpretado;
* classificado;
* encaminhado;
* registrado.

---

# Onde os LLMs entram

## LLMs adicionam compreensão de linguagem aos workflows

```text id="robb9f"
Texto/documento
        ↓
LLM interpreta
        ↓
JSON estruturado
        ↓
Workflow automatiza
```

---

# O que é um LLM?

## Large Language Model

Modelos treinados para:

* entender linguagem;
* interpretar contexto;
* gerar texto;
* estruturar informações;
* classificar conteúdo.

---

# Na prática...

LLMs funcionam como:

# Motores de interpretação de texto

Eles conseguem entender:

* e-mails;
* XML;
* SPED;
* contratos;
* notas;
* mensagens;
* extratos.

---

# Analogia simples

## OCR vs LLM

### OCR

Lê caracteres.

### LLM

Entende significado.

---

# O que um LLM consegue fazer?

| Entrada          | Saída                   |
| ---------------- | ----------------------- |
| E-mail           | Intenção                |
| XML NF-e         | Dados estruturados      |
| SPED             | Explicação simplificada |
| Extrato bancário | Categoria financeira    |
| Contrato         | Resumo operacional      |

---

# O insight mais importante

# LLMs transformam linguagem humana em dados estruturados

---

# O que é um Prompt?

## Prompt = instrução operacional para o modelo

É a forma como definimos:

* comportamento;
* contexto;
* objetivo;
* formato da resposta.

---

# Analogia prática

## Prompt é como um procedimento operacional

Sem instruções claras:

* respostas inconsistentes;
* baixa previsibilidade;
* difícil automação.

Com instruções claras:

* respostas previsíveis;
* integração facilitada;
* automação confiável.

---

# Exemplo de Prompt RUIM

```txt id="61u0f8"
Analise esse e-mail
```

---

# Exemplo de Prompt BOM

```txt id="wiqyha"
Você é um assistente operacional contábil.

Analise o e-mail abaixo e identifique:
- tipo da solicitação
- urgência
- cliente
- ação necessária

Retorne APENAS JSON.
```

---

# Estrutura de um bom Prompt

| Elemento   | Objetivo        |
| ---------- | --------------- |
| Papel      | contexto        |
| Tarefa     | ação            |
| Restrições | previsibilidade |
| Formato    | automação       |

---

# Prompt Engineering

## Não é “escrever bonito”

É:

# Produzir saída previsível para automação

---

# Por que JSON é importante?

Porque workflows precisam de:

* previsibilidade;
* estrutura;
* integração.

---

# Fluxo moderno de automação com IA

```text id="g3rdzf"
Prompt
    ↓
LLM interpreta
    ↓
JSON estruturado
    ↓
Workflow automatiza
```

---

# Modelos Abertos vs Fechados

| Tipo     | Exemplos             |
| -------- | -------------------- |
| Fechados | GPT, Claude, Gemini  |
| Abertos  | Llama, Qwen, Mistral |

---

# Modelos Fechados

## Vantagens

* maior facilidade;
* alta qualidade;
* infraestrutura pronta.

## Desvantagens

* custo por uso;
* dependência do fornecedor;
* dados enviados para terceiros.

---

# Modelos Abertos

## Vantagens

* execução local;
* maior privacidade;
* mais controle;
* menor custo contínuo.

## Desvantagens

* exigem hardware;
* configuração mais técnica;
* manutenção da infraestrutura.

---

# Stack utilizada

* n8n
* LM Studio
* Qwen 3 9B

---

# Infraestrutura da oficina

## Stack utilizada

* n8n
* LM Studio
* Modelo LLM local
* Google Sheets

---

# Arquitetura da oficina

```text id="2i4h2q"
Participantes
      ↓
n8n
      ↓
LLM local (LM Studio)
      ↓
JSON estruturado
      ↓
Google Sheets
```

---

# Workflow 1

# Triagem Inteligente de E-mails

---

# Problema real

Escritórios recebem:

* notas fiscais;
* dúvidas;
* comprovantes;
* solicitações;
* cobranças;
* pendências.

Tudo misturado.

---

# Objetivo da automação

Identificar automaticamente:

* tipo da solicitação;
* cliente;
* urgência;
* ação necessária.

---

# Arquitetura do workflow

```text id="eiiy9u"
Webhook simulando e-mail
        ↓
LLM interpreta conteúdo
        ↓
JSON estruturado
        ↓
Switch no n8n
        ↓
Google Sheets
```

---

# Entrada do workflow

```txt id="kk26s7"
Bom dia.

Segue nota fiscal referente aos serviços prestados em maio.

Att.
Empresa XPTO
```

---

# Saída estruturada

```json id="9goetu"
{
  "tipo": "envio_nota_fiscal",
  "cliente": "Empresa XPTO",
  "urgencia": "normal",
  "acao": "registrar_documento"
}
```

---

# O que o workflow pode fazer?

Após interpretar o conteúdo:

* salvar em planilha;
* encaminhar setor;
* registrar pendência;
* gerar tarefa;
* responder automaticamente.

---

# O papel do n8n

O LLM interpreta.

O n8n:

* executa ações;
* integra sistemas;
* automatiza processos;
* orquestra workflows.

---

# Insight importante

## LLM NÃO é o sistema final

Ele funciona como:

* interpretador;
* classificador;
* extrator;
* motor inicial de decisão.

---

# Workflow 2

# XML NF-e → Interpretação Inteligente

---

# Problema real

XML fiscal é:

* verboso;
* técnico;
* difícil de interpretar manualmente.

---

# Objetivo

Transformar XML em informação operacional.

---

# Fluxo do workflow

```text id="ij72bn"
XML NF-e
      ↓
LLM interpreta
      ↓
JSON estruturado
      ↓
Google Sheets
```

---

# Exemplo de XML

```xml id="s0mv7j"
<emit>
  <xNome>POSTO CENTRAL</xNome>
</emit>
```

---

# Saída estruturada

```json id="ac01j6"
{
  "fornecedor": "POSTO CENTRAL",
  "categoria": "Combustível",
  "valor": 450.00,
  "possivel_centro_custo": "Frota"
}
```

---

# O que isso demonstra?

O modelo consegue:

* entender estrutura;
* interpretar contexto;
* extrair significado;
* transformar texto em dados acionáveis.

---

# Isso funciona também para

* SPED;
* contratos;
* boletos;
* extratos;
* comprovantes;
* legislações.

---

# Aplicações reais de alto impacto

---

# 1. Triagem automática de e-mails

* classificação;
* roteamento;
* registro;
* priorização.

---

# 2. Classificação financeira automática

Exemplo:

```txt id="vlhw3r"
AUTO POSTO CENTRAL
```

↓

```json id="zgbwe1"
{
  "categoria": "Combustível"
}
```

---

# 3. Extração documental

* XML;
* PDF;
* notas;
* contratos.

---

# 4. Auditoria preliminar

Identificação de:

* inconsistências;
* incompatibilidades;
* possíveis riscos fiscais.

---

# 5. Organização documental inteligente

IA identifica:

* NF;
* boleto;
* DARF;
* contrato;
* comprovante.

---

# 6. Comunicação automatizada

* cobrança;
* pendência fiscal;
* solicitação documental;
* avisos automáticos.

---

# O que muda no escritório?

## Antes

Humano:

* lê;
* interpreta;
* classifica;
* encaminha;
* registra.

---

# Depois

LLM:

* interpreta;
* estrutura;
* roteia.

Humano:

* valida;
* supervisiona;
* decide.

---

# O papel do contador muda

## A IA NÃO substitui o contador

Mas reduz:

* tarefas repetitivas;
* trabalho operacional manual;
* retrabalho;
* triagem manual.

---

# Curto prazo

Aplicações já viáveis hoje:

* triagem documental;
* classificação financeira;
* leitura XML;
* automação operacional;
* respostas automáticas.

---

# Médio prazo

Evoluções possíveis:

* copilotos internos;
* RAG com legislação;
* workflows fiscais inteligentes;
* auditoria assistida por IA.

---

# Insight final

# LLMs não substituem sistemas contábeis

# Eles adicionam compreensão de linguagem aos workflows

---

# Encerramento

## O futuro da automação contábil

```text id="go9b0g"
Texto
    ↓
LLM entende
    ↓
Workflow executa
    ↓
Humano supervisiona
```

---

# Obrigado!

## Perguntas?
