# Configuracao do Google Sheets

Use uma unica planilha para a oficina.

## 1. Criar a planilha

No Google Sheets, crie uma planilha chamada:

```text
Oficina IA Contabilidade
```

Crie exatamente estas abas:

```text
triagem_emails
notas_fiscais
pendencias
```

## 2. Criar os cabecalhos

Na aba `triagem_emails`, use:

```text
tipo, cliente, competencia, urgencia, acao, assunto
```

Na aba `notas_fiscais`, use:

```text
fornecedor, cnpj, valor_total, competencia, categoria
```

Na aba `pendencias`, use:

```text
cliente, pendencia, mensagem, status
```

## 3. Opcional: importar exemplos

Voce pode importar estes CSVs para preencher exemplos iniciais:

- `dados/planilhas/template-triagem-emails.csv`
- `dados/planilhas/template-notas-fiscais.csv`
- `dados/planilhas/template-pendencias.csv`

No Google Sheets:

1. Abra a aba desejada.
2. Va em `Arquivo > Importar`.
3. Envie o CSV correspondente.
4. Escolha `Substituir dados na celula selecionada`.

## 4. Copiar o ID da planilha

Na URL da planilha:

```text
https://docs.google.com/spreadsheets/d/ID_DA_PLANILHA/edit
```

Copie apenas o trecho `ID_DA_PLANILHA`.

## 5. Configurar no n8n

Em cada node do Google Sheets:

1. Selecione ou crie a credencial Google Sheets.
2. Troque `COLE_AQUI_O_ID_DA_PLANILHA` pelo ID real.
3. Confira se o nome da aba esta correto:
   - `triagem_emails`
   - `notas_fiscais`
   - `pendencias`

## 6. Teste rapido

Execute primeiro o fluxo 03.

Entrada sugerida:

```json
{
  "cliente": "XPTO LTDA",
  "pendencia": "XML da competencia 05/2026 nao enviado"
}
```

Se uma nova linha aparecer na aba `pendencias`, a conexao esta funcionando.
