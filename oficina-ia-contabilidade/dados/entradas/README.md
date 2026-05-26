# Entradas de teste dos fluxos

Use estes exemplos para testar os webhooks no n8n.

Quando o workflow estiver em modo teste, use a URL de teste exibida pelo n8n.
Quando estiver ativo, use:

```text
http://localhost:5678/webhook/NOME_DO_WEBHOOK
```

## Fluxo 00 - agente simples

Webhook:

```text
fluxo-00-agente-simples
```

Exemplo:

```bash
curl -X POST http://localhost:5678/webhook/fluxo-00-agente-simples \
  -H "Content-Type: application/json" \
  -d @dados/entradas/fluxo-00/pergunta-lucro-presumido.json
```

## Fluxo 01 - triagem de emails

Webhook:

```text
fluxo-01-triagem-emails
```

Exemplo:

```bash
curl -X POST http://localhost:5678/webhook/fluxo-01-triagem-emails \
  -H "Content-Type: application/json" \
  -d @dados/entradas/fluxo-01/email-envio-xml.json
```

## Fluxo 02 - extracao de NF-e XML

Webhook:

```text
fluxo-02-extracao-nfe-xml
```

Este fluxo espera um JSON com o XML no campo `xml`.

Exemplo:

```bash
curl -X POST http://localhost:5678/webhook/fluxo-02-extracao-nfe-xml \
  -H "Content-Type: application/json" \
  -d @dados/entradas/fluxo-02/nfe-alves-varejo-json.json
```

## Fluxo 03 - geracao de pendencias

Webhook:

```text
fluxo-03-geracao-pendencias
```

Exemplo:

```bash
curl -X POST http://localhost:5678/webhook/fluxo-03-geracao-pendencias \
  -H "Content-Type: application/json" \
  -d @dados/entradas/fluxo-03/pendencia-xml-maio.json
```
