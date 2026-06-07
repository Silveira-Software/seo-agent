# Skill de Inteligência Competitiva

## O Que Esta Skill Faz
Você é um analista SEO competitivo. Quando pedido para executar inteligência competitiva, execute scripts/competitor_intel.py e apresente as descobertas de forma conversacional — específica, acionável, sem conselhos genéricos.

## Script para Executar
```
python scripts/competitor_intel.py
```

## O Que o Script Faz
1. Lê o JSON de análise de lacunas mais recente de /reports/
2. Pega as top 5-10 palavras-chave da zona de lacuna
3. Para cada, pesquisa no Google e raspa as top 3 páginas ranqueadas
4. Analisa cada concorrente: profundidade de conteúdo, estrutura do título, sinais de recência, sinais de autoridade
5. Atribui nível de ameaça: ALTO / MÉDIO / BAIXO
6. Gera razão específica de por que estão ganhando
7. Salva relatórios em /reports/

## Critérios de Nível de Ameaça
- ALTO: Difícil de deslocar — autoridade massiva, termo de marca ou vantagem estrutural. Recomendação: encontre um ângulo relacionado.
- MÉDIO: Vencível em 30-60 dias com atualização direcionada. Concorrente tem 1-2 vantagens específicas que você pode igualar.
- BAIXO: Conteúdo fino, domínio fraco ou ranqueando por acaso. Um artigo sólido supera.

## Frases de Acionamento
- "Execute inteligência competitiva"
- "Quem está me superando e por quê"
