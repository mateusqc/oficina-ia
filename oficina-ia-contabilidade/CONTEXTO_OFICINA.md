# Oficina — IA Aplicada à Contabilidade

## Objetivo

Esta oficina tem como objetivo introduzir conceitos práticos de IA Generativa aplicada à rotina operacional de escritórios contábeis.

O foco NÃO é:
- teoria profunda de IA;
- matemática;
- treinamento de modelos;
- ciência de dados.

O foco é:
- automação operacional;
- workflows;
- LLMs;
- prompts;
- interpretação de documentos;
- tomada de decisão automatizada;
- integração de IA com processos reais.

---

# Público-alvo

Perfil misto:
- contadores;
- profissionais administrativos;
- profissionais de TI;
- analistas;
- pessoas sem background técnico profundo.

A oficina deve assumir:
- pouca familiaridade com programação;
- conhecimento básico de ferramentas digitais;
- familiaridade com documentos fiscais e rotina contábil.

---

# Duração

Aproximadamente 1 hora.

---

# Narrativa da oficina

A oficina deve seguir uma progressão pedagógica clara:

1. IA conversando
2. IA interpretando intenção
3. IA lendo documentos
4. IA automatizando operação

O conceito central da oficina é:

"LLMs transformam linguagem natural e documentos em dados estruturados acionáveis."

---

# Stack tecnológica

## Infraestrutura

Toda a infraestrutura será hospedada localmente em um MacBook Apple Silicon M5.

Os participantes acessarão via navegador na mesma rede local.

---

## Componentes

### n8n
Responsável pelos workflows e automações.

### LM Studio
Responsável por servir o modelo LLM localmente via API compatível com OpenAI.

### Google Sheets
Utilizado como:
- armazenamento visual;
- persistência simples;
- visualização dos resultados dos workflows.

---

# Modelo LLM

## Modelo sugerido

Qwen2.5 7B Instruct

---

## Requisitos importantes

- respostas rápidas;
- prompts curtos;
- baixa latência;
- structured output;
- respostas determinísticas.

---

# Filosofia da oficina

## NÃO fazer

- integrações complexas;
- APIs reais de ERPs;
- automações críticas;
- autenticações complicadas;
- workflows excessivamente longos;
- OCR complexo;
- parsing completo de SPED.

---

## Fazer

- workflows pequenos;
- visualmente claros;
- fortemente conectados à rotina contábil;
- com alto impacto demonstrativo.

---

# Fluxos da oficina

## Fluxo 0 — Agente conversacional simples

Objetivo:
- apresentar LLM;
- demonstrar integração básica n8n + LM Studio;
- introduzir prompts.

Fluxo:

Webhook/Chat → LLM → Resposta

---

## Fluxo 1 — Triagem inteligente de e-mails contábeis

Objetivo:
- mostrar IA interpretando intenção;
- structured output;
- automação operacional.

Fluxo:

Webhook simulando e-mail
→ LLM
→ JSON estruturado
→ Switch
→ Google Sheets

Exemplos:
- envio de XML;
- dúvida fiscal;
- cobrança;
- pendência documental;
- solicitação de folha.

---

## Fluxo 2 — Extração de dados de nota fiscal PDF

Objetivo:
- mostrar IA lendo documento real;
- extração estruturada;
- automação documental.

Fluxo:

Upload PDF
→ Extração texto
→ LLM
→ JSON estruturado
→ Google Sheets

Campos esperados:
- fornecedor;
- CNPJ;
- valor;
- competência;
- categoria.

---

## Fluxo 3 — Geração automática de comunicação de pendências

Fluxo reserva caso haja tempo.

Objetivo:
- mostrar IA gerando comunicação contextual;
- automação operacional.

Fluxo:

Pendência
→ LLM
→ Mensagem profissional
→ Google Sheets

---

# Integração com ERP contábil

NÃO implementar integrações reais.

Apenas comentar conceitualmente sobre:
- Domínio;
- ERPs contábeis;
- automação antes/depois do ERP;
- IA como camada operacional.

Mensagem principal:

"O ERP continua sendo o sistema principal. A IA automatiza interpretação, organização e tomada inicial de decisão."

---

# Pesquisa inicial dos participantes

Será utilizado Mentimeter.

Objetivo:
- medir maturidade técnica;
- ajustar profundidade da oficina;
- gerar engajamento inicial.

Perguntas:
- Você sabe programar?
- Sua atuação profissional está mais alinhada com:
  - Contador
  - TI
  - Outro
- Qual seu nível de familiaridade com IA generativa?
- Qual tarefa contábil mais consome tempo hoje?
- O que você mais espera sair sabendo?

Participantes utilizarão smartphones via QR code.

---

# Diretrizes para os materiais

## Slides

- pouco texto;
- visual;
- foco em narrativa;
- exemplos reais;
- linguagem simples;
- foco em operação e produtividade.

---

## Workflows

- pequenos;
- bem nomeados;
- didáticos;
- fáceis de entender posteriormente.

Os arquivos `.json` dos workflows serão considerados fonte de verdade pós-oficina.

---

# Estrutura esperada do projeto

oficina-ia-contabilidade/
├── docker/
├── dados/
├── fluxos/
├── slides/
├── docs/
├── README.md
├── CONTEXTO_OFICINA.md
├── REQUISITOS.md
└── PROMPT_CODEX.md
