# Agente SEO — mikefutia.com

## O Que é Este Projeto
Um sistema de inteligência SEO que conecta ao Google Search Console, identifica lacunas de palavras-chave, mapeia concorrentes e gera um plano de conteúdo semanal e um dashboard HTML — tudo a partir de um único prompt.

## Protocolo de Início de Sessão
No início de cada sessão:
1. Leia o(s) arquivo(s) de skill relevantes para a tarefa de hoje
2. Leia brand-voice.md antes de qualquer tarefa de conteúdo
3. Verifique /reports/ para as saídas mais recentes antes de executar skills downstream

## Skills Disponíveis
- skills/gap-finder.md — descoberta de palavras-chave, análise de zonas de lacuna, recomendações de ação
- skills/competitor-intel.md — inteligência competitiva, níveis de ameaça, por que estão ganhando
- skills/brand-writer.md — planejamento de conteúdo, redação de artigos, voz da marca

## Comandos-Chave
- "Execute a análise de lacunas desta semana" → lê skills/gap-finder.md, executa scripts/gap_finder.py
- "Execute inteligência competitiva" → lê skills/competitor-intel.md, executa scripts/competitor_intel.py
- "Gere o plano de conteúdo desta semana" → lê skills/brand-writer.md, executa scripts/content_plan.py
- "Construa o dashboard" → executa scripts/build_dashboard.py usando os relatórios da semana
- "Execute o workflow semanal completo" → executa todos os quatro em sequência, constrói o dashboard no final

## Estrutura de Arquivos
skills/             — arquivos de instrução de skills (Claude lê antes de agir)
scripts/            — scripts Python que Claude executa para produzir saídas
reports/            — saídas semanais salvas como .md e .json
drafts/             — rascunhos de artigos pendentes de revisão
brand-voice.md      — perfil de voz da marca (atualizar semanalmente)
.env                — credenciais de API (nunca faça commit)

## Credenciais de API (definir no .env)
GSC_CLIENT_SECRET_FILE=credentials.json   # Client secret OAuth do Google
GSC_SITE_URL=sc-domain:mikefutia.com      # Sua propriedade do Search Console
DATAFORSEO_LOGIN=seu_login                # Opcional — melhora dados de volume
DATAFORSEO_PASSWORD=sua_senha             # Opcional

## Regra de Formato de Saída
Todo script salva dois arquivos:
1. Um relatório .md legível por humanos → /reports/
2. Um arquivo de dados .json legível por máquina → /reports/
O construtor de dashboard lê os arquivos .json para renderizar a saída HTML.
