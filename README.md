# Arquitetura híbrida para detecção de tráfego malicioso em ambientes IoT

**Simpósio de Integração Acadêmica (SIA UFV 2026) — Trabalho 24615**

**Matheus Antony Souza Pereira** · Orientação: **Vitor Barbosa Carlos de Souza**  
Departamento de Informática — Universidade Federal de Viçosa (UFV)  
Pesquisa · Graduação · ODS 9 — Indústria, Inovação e Infraestrutura · PIBIC/CNPq

### Painel

**[Visualizar o painel em PDF](apresentacao/painel-final-sia-2026.pdf)** (90 × 120 cm)

Apresentação programada para **21 de outubro de 2026, das 10h30 às 12h**, no **Espaço Multiuso**, painel **187**.

[Resumo aprovado pelo SIA](docs/resumo-aprovado.md)

## Sobre a pesquisa

O trabalho investiga se conexões de rede IoT podem ser agrupadas sem o uso prévio de rótulos e se esses grupos correspondem ao tráfego normal e às famílias de ataques.

Foram analisadas **211.043 conexões** do **TON_IoT**, distribuídas em dez classes. O conjunto foi dividido em treinamento, validação e teste por grupos definidos pela combinação `src_ip|dst_ip|service|proto`.

A abordagem tem duas etapas:

1. **Agrupamento:** comparação entre K-Means, DBSCAN e agrupamento hierárquico, com seleção do **MiniBatch K-Means (k = 30)**.
2. **Classificação:** treinamento de **Random Forest** para prever tráfego normal/malicioso (`label`), família do ataque (`type`) e agrupamento (`cluster_kmeans30`).

![Arquitetura da abordagem em duas fases](figuras/arquitetura-duas-fases.png)

## Resultados

| Medida no conjunto de teste | Resultado |
| --- | ---: |
| AMI — clusters × tipos de ataque | 0,6023 |
| AMI — clusters × normal/malicioso | 0,3692 |
| Macro-F1 — classificação binária | 0,9993 |
| Macro-F1 — classificação por tipo | 0,9525 |
| Macro-F1 — predição dos clusters | 0,7648 |

Na **predição dos clusters**, a macro-F1 foi **0,9993** na validação cruzada convencional e **0,7967** na validação por grupos. Essa diferença reforça a importância de evitar que grupos de conexões semelhantes sejam compartilhados entre treinamento e avaliação.

| F1 por tipo de ataque | Pureza dos clusters |
| --- | --- |
| ![F1 por tipo de ataque](figuras/f1-por-classe.png) | ![Pureza dos clusters](figuras/pureza-por-cluster.png) |

[Ver matriz de confusão por tipo](figuras/matriz-confusao-tipo.png) · [Origem das figuras](figuras/README.md)

A computação em névoa é considerada como contexto de aplicação. **Não houve implantação em gateways reais** nesta etapa.

## Trabalhos relacionados

- [SBCUP 2026 — código, métricas e figuras do experimento](https://github.com/Math-BUG/iot-fog-ids-two-phase)
- [ERAD-SE 2026 — avaliação de desempenho CPU/GPU](https://github.com/Math-BUG/experimento_erad)
- [Generalização de IDS — continuidade da pesquisa](https://github.com/Math-BUG/ids_generalization_pipeline)

**Publicação relacionada:** PEREIRA, M. A. S.; SOUZA, V. B.; FERNANDES, D. L. *Abordagem em duas fases para detecção e classificação de ataques em redes IoT com computação em névoa*. SBCUP, 2026.
