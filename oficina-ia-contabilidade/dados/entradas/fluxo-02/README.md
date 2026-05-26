# Entradas do fluxo 02

O fluxo 02 espera um JSON com o XML no campo `xml`.

Mocks prontos:

- `nfe-alves-varejo-json.json`
- `nfe-costa-servicos-json.json`
- `nfe-nunes-decor-json.json`
- `colecao-xml-json.json`

Exemplos:

```bash
curl -X POST http://localhost:5678/webhook/fluxo-02-extracao-nfe-xml \
  -H "Content-Type: application/json" \
  -d @dados/entradas/fluxo-02/nfe-alves-varejo-json.json
```

```bash
curl -X POST http://localhost:5678/webhook/fluxo-02-extracao-nfe-xml \
  -H "Content-Type: application/json" \
  -d @dados/entradas/fluxo-02/nfe-costa-servicos-json.json
```

```bash
curl -X POST http://localhost:5678/webhook/fluxo-02-extracao-nfe-xml \
  -H "Content-Type: application/json" \
  -d @dados/entradas/fluxo-02/nfe-nunes-decor-json.json
```
