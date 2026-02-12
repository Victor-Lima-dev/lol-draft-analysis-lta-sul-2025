# Análise: Meta de Draft — Campeões Sub-Utilizados na LTA S

## Pergunta
**"Quais campeões têm win rate consistente acima de 53% no cenário competitivo global de 2025 e estão sendo sub-utilizados na LTA S?"**

## Dataset
- **Fonte:** Oracle's Elixir — 2025 LoL Esports Match Data
- **Escopo global:** 10 ligas competitivas (LCKC, LCK, LCP, LEC, TCL, LTA N, PCS, LTA, VCS, LPLOL)
- **Escopo regional:** LTA S (liga sul-americana)
- **Linhas utilizadas:** Jogadores (position ≠ 'team') para picks/WR, times (position == 'team') para bans
- **Segmentação por posição:** Cada campeão é associado à posição (role) em que foi jogado (top, jng, mid, bot, sup)
- **Filtros de qualidade:**
  - Amplitude de IC 95% ≤ 0.20 (confiabilidade estatística do WR)
  - Mínimo de 25 partidas por campeão
- **Métricas:** Win Rate, Pick Rate, Ban Rate, Presence Rate (Pick + Ban), Percentil de Presence, Position (role)

## Metodologia

1. Geração de tabelas de picks/bans/WR separadas para o pool global e para a LTA S
2. Cálculo de intervalo de confiança de 95% para o win rate de cada campeão
3. Filtragem por confiabilidade: amplitude IC ≤ 0.20 e n > 25 partidas
4. Merge entre tabelas global e LTA S, com cálculo de gap de presence e percentis
5. Isolamento de campeões com WR global ≥ 53%, presence LTA S < 30%

## Descoberta Principal

**3 campeões** apresentam win rate global ≥ 53%, presença relevante no meta competitivo global (presence rate ≥ 10%), e gap significativo em relação à LTA S.

| Campeão | Posição | WR Global | IC Amplitude | WR LTA S | Presence Global | Percentil Global | Presence LTA S | Percentil LTA S | Gap |
|---------|---------|-----------|--------------|----------|-----------------|------------------|----------------|-----------------|-----|
| **Zyra** | jng | 55% | 0.17 | 43% | 18% | 35 | 7% | 12 | 11 p.p. |
| **Nidalee** | jng | 53% | 0.17 | 67% | 12% | 21 | 3% | 3 | 9 p.p. |
| **Renata Glasc** | sup | 54% | 0.13 | 43% | 16% | 30 | 9% | 16 | 7 p.p. |

**Nota:** Os demais campeões com WR ≥ 53% (Xayah, Ziggs, Yunara, Caitlyn, Maokai, Renekton, Annie, Camille) apresentam gap de presence ≤ 2 p.p. ou gap negativo, indicando alinhamento entre meta global e regional.

## Análise dos Candidatos

### Zyra (jng) — Caso mais expressivo
- **Posição:** Jungle — recomendação direcionada ao jogador de jng do time
- Maior gap de presence: 11 p.p. (18% global → 7% LTA S)
- Percentil global 35 indica uma pick relevante no meta, não de nicho
- Na LTA S cai para percentil 12 — sub-utilização consistente
- **Porém:** WR na LTA S é 43%, amostra insuficiente para conclusão regional

### Renata Glasc (sup) — Maior confiabilidade estatística
- **Posição:** Suporte — recomendação direcionada ao jogador de sup do time
- IC global mais apertado do grupo: 0.13 (amplitude)
- Percentil 30 global → 16 LTA S — gap de 7 p.p.
- WR na LTA S é 43%, amostra igualmente pequena regionalmente
- **Destaque:** WR de 54% é o mais confiável estatisticamente entre os três candidatos

### Nidalee (jng) — Caso mais delicado
- **Posição:** Jungle — mesma role que Zyra, competem pelo mesmo slot no draft
- Percentil global 21 indica pick mais situacional, não consolidada no meta
- Gap extremo: percentil 3 na LTA S — a região praticamente ignora o campeão
- WR na LTA S é 67% (amostra muito pequena, sem significância estatística)
- **Risco:** Campeão de perfil técnico exigente — a análise não captura se existem jogadores na região capazes de executá-lo em nível competitivo

> [!IMPORTANT]
> **Insight de posição:** 2 dos 3 campeões sub-utilizados são de **jungle** (Zyra e Nidalee). Isso sugere que a LTA S pode ter um gap específico no pool de jungle em relação ao meta global. Renata Glasc é o único campeão de suporte identificado.

## Campeões Alinhados (sem gap relevante)

| Campeão | WR Global | WR LTA S | Presence Global | Presence LTA S | Gap |
|---------|-----------|----------|-----------------|----------------|-----|
| Xayah | 56% | 56% | 22% | 20% | +2 p.p. |
| Maokai | 53% | 54% | 23% | 25% | -2 p.p. |
| Renekton | 56% | 59% | 22% | 27% | -5 p.p. |
| Annie | 56% | 48% | 17% | 23% | -6 p.p. |
| Camille | 58% | 55% | 5% | 12% | -7 p.p. |

Estes campeões mostram que a LTA S está **alinhada ou à frente** do meta global em boa parte das picks. A região não possui um desalinhamento generalizado com o cenário competitivo — os gaps identificados são pontuais.

## Conclusão

Identificamos 3 campeões com win rate global ≥ 53% (IC 95% com amplitude ≤ 0.20) e gap positivo de presence entre o cenário global e a LTA S:

**Zyra (jng)** e **Renata Glasc (sup)** estão no percentil 30-35 de presence global, indicando que são parte do meta competitivo de 2025, não picks de nicho. A LTA S as coloca no percentil 12-16 — significativamente abaixo.

**Nidalee (jng)** é mais situacional (percentil 21 global), mas seu gap é o mais extremo: percentil 3 na LTA S. A região praticamente não utiliza esse campeão. Notavelmente, **2 dos 3 campeões identificados são de jungle**, sugerindo um gap específico nessa posição na LTA S.

Estas são **hipóteses prioritárias para investigação pelo coaching staff**, não conclusões definitivas. O valor analítico está na identificação de direções de investigação: campeões com sinal positivo de WR global e baixa familiaridade regional criam potencial vantagem de draft por imprevisibilidade — desde que o time tenha ou possa desenvolver proficiência nos picks.

## Limitações

1. **WR global sumariza regiões com metas e estilos distintos** — LCK/LPL dominam numericamente o pool, então "global" reflete principalmente o meta asiático
2. **Não controla por matchup ou composição de draft** — campeões podem ter WR inflado por serem pickados predominantemente em situações favoráveis
3. **Presence baixa na LTA S pode refletir falta de proficiência** dos jogadores da região, não inviabilidade do pick
4. **Janela temporal agregada** — patches de LoL alteram o meta com frequência mensal; esta análise não segmenta por patch e pode agregar metas incompatíveis
5. **Amostra da LTA S é pequena** para os campeões identificados (7, 6, 12 partidas), impossibilitando conclusões sobre WR regional

## Próximos Passos

- [x] ~~Segmentar análise por **posição** (sup/jng/mid) para direcionar recomendações ao role correto~~ — **Feito:** coluna `position` adicionada. Resultado: 2 junglers (Zyra, Nidalee) + 1 suporte (Renata Glasc)
- [ ] Filtrar por **patches recentes** para capturar meta atual
- [ ] Investigar **WR destes campeões por liga** (LCK, LEC, LPL isoladamente)
- [ ] Analisar **matchups** favoráveis e desfavoráveis de cada campeão
