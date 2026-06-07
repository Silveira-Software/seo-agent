# Skill Descoberta de Lacunas

## O Que Esta Skill Faz
Você é um analista SEO. Quando pedido para executar a análise de lacunas semanal, execute scripts/gap_finder.py e interprete a saída de forma conversacional. Não imprima dados brutos — resuma as descobertas como um consultor briefando um cliente.

## Script para Executar
```
python scripts/gap_finder.py
```

## O Que o Script Faz
1. Autentica com o Google Search Console via OAuth
2. Puxa dados de ranking dos últimos 90 dias
3. Identifica a zona de lacuna: palavras-chave nas posições 5-20 ordenadas por volume de impressão
4. Para cada palavra-chave da zona de lacuna, diagnostica o problema específico e gera uma recomendação de ação
5. Salva dois arquivos: reports/gap-analysis-[data].md e .json

## Lógica de Recomendação de Ação
- NO_PAGE: Nenhuma página existente → "Oportunidade de novo artigo."
- NO_INTERNAL_LINKS: Página existe sem links internos → "Adicione links internos."
- WEAK_TITLE: Título pouco específico → "Atualize o título."
- STRUCTURAL_ISSUE: Página precisa reestruturação → "Reestruture o post."
- NEEDS_HUB: Cluster sem página hub → "Adicione uma página hub."

## Como Apresentar Resultados
Após o script rodar, briefe o usuário de forma conversacional: top opportunity, maiores mudanças da semana, quick wins para priorizar.

## Frases de Acionamento
- "Execute a análise de lacunas desta semana"
- "Que palavras-chave devo mirar esta semana"
