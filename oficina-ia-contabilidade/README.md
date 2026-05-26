# Oficina IA Aplicada à Contabilidade

Infraestrutura inicial para uma oficina prática de IA generativa aplicada à rotina de escritórios contábeis.

A ideia da oficina é mostrar, de forma simples, como LLMs podem transformar linguagem natural e documentos em dados estruturados acionáveis usando:

- n8n para automações;
- LM Studio para rodar o modelo localmente;
- Google Sheets para visualizar resultados.

## Roteiro dos participantes

### 1. Acessar o n8n

Abra no navegador:

```text
https://suited-elf-unduly.ngrok-free.app
```

Entre no workflow indicado pelo instrutor.

### Contas dos participantes

Use um convite por participante. Ao abrir o link, defina a senha sugerida:

```text
Oficina123
```

Planilha de controle dos participantes:

```text
https://docs.google.com/spreadsheets/d/1pczl1PGou7zDOS6t6qs9iSBBAKXh94trEqbE5qSp1Ms/edit?usp=sharing
```

### 2. Atividade 1 - Triagem de e-mails

Objetivo: ver a IA classificando uma mensagem.

Use um exemplo da pasta:

```text
dados/entradas/fluxo-01/
```

Exemplo de entrada:

```json
{
  "cliente": "Alves Varejo Ficticio Ltda",
  "assunto": "XMLs das vendas de abril",
  "corpo": "Bom dia. Seguem anexos os XMLs das notas de venda emitidas em abril."
}
```

Observe a saída esperada:

```json
{
  "tipo": "envio_xml",
  "cliente": "Alves Varejo Ficticio Ltda",
  "competencia": "2026-04",
  "urgencia": "normal",
  "acao": "registrar recebimento dos XMLs"
}
```

### 3. Atividade 2 - Interpretação de XML NF-e

Objetivo: transformar XML fiscal em dados estruturados.

Use um mock da pasta:

```text
dados/entradas/fluxo-02/
```

O JSON deve ter este formato:

```json
{
  "arquivo": "nfe-exemplo.xml",
  "xml": "<NFe>...</NFe>"
}
```

Observe os campos extraídos:

```text
fornecedor, cnpj, valor_total, competencia, categoria
```

### 4. Atividade 3 - Comunicação de pendências - Opcional

Objetivo: gerar uma mensagem profissional a partir de uma pendência.

Use um exemplo da pasta:

```text
dados/entradas/fluxo-03/
```

Exemplo:

```json
{
  "cliente": "XPTO LTDA",
  "pendencia": "XML da competencia 05/2026 nao enviado"
}
```

Confira a mensagem gerada e o registro no Google Sheets.

### 5. Resultado esperado

Ao final das atividades, você deve conseguir enxergar este padrão:

```text
Texto ou documento
        ↓
IA interpreta
        ↓
JSON estruturado
        ↓
n8n automatiza
        ↓
Google Sheets registra
```

## Pré-requisitos

- Docker Desktop instalado e aberto.
- Navegador atualizado.
- Conta Google para usar Google Sheets.
- LM Studio instalado no computador.

## Como subir o ambiente

No terminal, entre na pasta do projeto:

```bash
cd oficina-ia-contabilidade/docker
docker compose up -d
```

Para verificar se o n8n subiu:

```bash
docker compose ps
```

Para parar:

```bash
docker compose down
```

Se o comando `docker compose` não existir na sua máquina, tente `docker-compose` nos mesmos comandos.

## Como acessar o n8n

Durante a oficina, abra no navegador:

```text
https://suited-elf-unduly.ngrok-free.app
```

Para uso local, abra:

```text
http://localhost:5678
```

No primeiro acesso, o n8n pode pedir a criação de um usuário local.

## Google Sheets

1. Crie uma planilha no Google Sheets para a oficina.
2. Crie abas simples, por exemplo:
   - `emails`
   - `notas_fiscais`
   - `pendencias`
3. No n8n, crie uma credencial do Google Sheets quando o workflow pedir.
4. Autorize o acesso usando sua conta Google.

Use dados fictícios durante a oficina. Não use informações reais de clientes.

## LM Studio

O LM Studio deve ser executado manualmente no host, fora do Docker.

Passos sugeridos:

1. Abra o LM Studio.
2. Baixe um modelo instrucional leve, como Qwen2.5 7B Instruct.
3. Inicie o servidor local compatível com OpenAI.
4. Confirme o endpoint local exibido pelo LM Studio.

Em workflows do n8n rodando dentro do Docker, use o host:

```text
http://host.docker.internal:1234/v1
```

## Estrutura

```text
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
```

## Troubleshooting

Se o n8n não abrir, confirme se o Docker Desktop está rodando e execute:

```bash
docker compose ps
docker compose logs n8n
```

Se a porta `5678` estiver ocupada, pare o processo que usa essa porta ou altere a porta no `docker-compose.yaml`.

Se o n8n não conseguir chamar o LM Studio, confira se o servidor do LM Studio está iniciado e se o workflow usa `host.docker.internal`, não `localhost`.

Se a autenticação do Google Sheets falhar, recrie a credencial no n8n e autorize novamente a conta Google.
