# Guia de Configuração

## Passo 1 — Instalar dependências
```bash
pip install -r requirements.txt
```

## Passo 2 — OAuth do Google Search Console (10 minutos)

1. Acesse https://console.cloud.google.com/
2. Crie um novo projeto (ou selecione existente)
3. Vá em **APIs e Serviços → Biblioteca**
4. Pesquise "Google Search Console API" → Ative
5. Vá em **APIs e Serviços → Credenciais**
6. Clique em **Criar Credenciais → ID do cliente OAuth**
7. Tipo de aplicação: **App para computador**
8. Baixe o arquivo JSON → renomeie para `credentials.json`
9. Coloque `credentials.json` na raiz desta pasta de projeto

## Passo 3 — Configurar seu arquivo .env
```bash
cp .env.example .env
```
Edite `.env` e defina:
- `GSC_SITE_URL` — URL da sua propriedade do Search Console
  - Para propriedades de domínio: `sc-domain:seudominio.com`
  - Para propriedades de prefixo URL: `https://www.seudominio.com/`

## Passo 4 — Primeira execução (aciona login OAuth no navegador)
```bash
python scripts/gap_finder.py
```
Uma janela do navegador abrirá pedindo autorização com sua conta Google.
Após autorizar, um arquivo `token.pickle` é salvo — você não precisará reautorizar.

## Passo 5 — Pedir ao Claude Code para executar o workflow
Abra o Claude Code nesta pasta de projeto e digite:
```
Execute a análise de lacunas desta semana
```

## Passo 6 — Executar o workflow semanal completo
```
Execute o workflow semanal completo
```
O Claude executará todos os três scripts em sequência e construirá o dashboard no final.

## Opcional — Configuração DataForSEO
Cadastre-se em https://dataforseo.com (pagamento por uso, ~$50/mês para uso típico).
Adicione login e senha ao `.env`.
Isso desbloqueia dados reais de volume de busca e análise de backlinks de concorrentes.
Sem ele, o sistema usa dados de impressão do GSC como proxy de volume — ainda muito útil.
