# Dashboard de Atividades — V1

O `DASHBOARD.html` permanece somente para consulta. Ele não altera atividades na planilha.

## Ativar a leitura do Google Sheets

1. Publique um Google Apps Script como Web App que devolva JSON.
2. No `DASHBOARD.html`, preencha `SHEETS_ENDPOINT` com a URL do Web App.
3. O dashboard consultará o endpoint ao abrir e a cada 60 segundos.

O retorno esperado é este objeto (também pode vir dentro de uma propriedade `data`):

```json
{
  "total": 67,
  "concluido": 62,
  "improdutivo": 5,
  "ultimo": {"site": "SP-NDI", "cidade": "Jundiaí", "status": "✓ Atividade concluída"},
  "deslocamento": {"site": "EUO", "cidade": "Montes Claros", "detalhe": "próxima atividade", "km": "385 km"},
  "proximos": [
    {"site": "EUO", "cidade": "Montes Claros", "tec": "V-1800"},
    {"site": "EUQ", "cidade": "Francisco Sá", "tec": "Z-700"},
    {"site": "EUN", "cidade": "Januária", "tec": "U-2100"}
  ],
  "hotel": {"nome": "Hotel Nova Aurora", "cidade": "Montes Claros", "valor": "R$ 118"},
  "km": {"dia": "195 km", "semana": "1.126 km", "mes": "5.466 km"}
}
```

Enquanto a URL não for configurada, a página usa dados demonstrativos e informa isso no rodapé.
