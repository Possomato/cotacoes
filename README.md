# Cotação de Obra — Casa Iperó

Aplicação web para cotação de materiais e mão de obra, com quantitativos extraídos diretamente do modelo Revit.

## Estrutura

```
cotacao-obra/
├── index.html   → interface da aplicação (não editar manualmente)
├── data.json    → quantitativos do projeto (alimentado pelo Revit)
├── prices.json  → seus preços salvos (gerado pelo botão "Exportar preços")
└── README.md
```

## Como usar

1. Abra `index.html` no navegador (ou acesse pelo GitHub Pages)
2. Preencha os preços unitários de cada item
3. Clique em **Salvar** — os preços ficam no localStorage do navegador
4. Use **Exportar preços** para gerar um `prices.json` de backup
5. Use **Importar preços** para restaurar um `prices.json` salvo anteriormente

## GitHub Pages

1. Crie um repositório no GitHub e faça push desta pasta
2. Em Settings → Pages → selecione a branch `main` e pasta `/root`
3. Acesse em `https://seu-usuario.github.io/nome-do-repo`

## Atualizar quantitativos do Revit

Quando o modelo Revit for alterado, o Claude extrai os novos quantitativos e atualiza **apenas o `data.json`** — o `index.html` e os seus preços salvos não são tocados.

### O que pode mudar no data.json:
- `qty` de cada item (quantidades reais do modelo)
- `_meta.ultima_atualizacao`
- `_meta.modelo_revit`
- Novos itens ou seções (se necessário)

### O que nunca muda automaticamente:
- Seus preços (`prices.json` / localStorage)
- O layout da página (`index.html`)
