# Arquitetura híbrida para detecção de tráfego malicioso em ambientes IoT

**Simpósio de Integração Acadêmica (SIA UFV 2026) — Trabalho 24615**

**Matheus Antony Souza Pereira** · Orientador: **Vitor Barbosa Carlos de Souza**  
Departamento de Informática · Universidade Federal de Viçosa (UFV)  
Pesquisa · Graduação · ODS 9 · Bolsa PIBIC/CNPq

**[Painel apresentado no SIA — PDF](apresentacao/painel-final-sia-2026.pdf)** · [Resumo aprovado](docs/resumo-aprovado.md) · **[Resultados detalhados](resultados/README.md)**

## Pesquisa

O estudo avalia uma abordagem em duas fases para analisar tráfego IoT. Primeiro, técnicas de **agrupamento não supervisionado** identificam padrões de conexão sem utilizar os rótulos de ataques. Depois, classificadores **Random Forest** predizem tráfego normal/malicioso (`label`), família do ataque (`type`) e o agrupamento atribuído pelo K-Means (`cluster_kmeans30`).

Foram analisadas **211.043 conexões do TON_IoT** (50.000 normais e 161.043 de nove famílias de ataques). A divisão foi realizada por grupos definidos pela chave composta `src_ip|dst_ip|service|proto`, resultando em 183.158 amostras de treino, 16.901 de validação e 10.984 de teste.

![Diagrama da arquitetura em duas fases](figuras/arquitetura-duas-fases.png)

## Resultados principais

### Alinhamento entre os clusters e os rótulos

Na etapa não supervisionada foi selecionado o **MiniBatch K-Means com `k = 30`**, após comparação com DBSCAN e agrupamento hierárquico. No **conjunto de teste**:

| Classes de referência | AMI | V-measure |
| --- | ---: | ---: |
| Tipos de ataque (`type`) | **0,6023** | 0,6041 |
| Normal/malicioso (`label`) | **0,3692** | 0,3696 |

O teste de permutação com 200 embaralhamentos encontrou **p = 0,0050** para o alinhamento entre os clusters e `type`. Os agrupamentos revelaram padrões associados a algumas classes, mas não produziram uma separação perfeita entre as famílias de ataques.

![Distribuição de tipos de ataque entre clusters](figuras/tipos-por-cluster.png)

### Classificação supervisionada

Resultados do **Random Forest no teste separado por grupos**:

| Tarefa | Acurácia | Macro-F1 | F1 ponderado |
| --- | ---: | ---: | ---: |
| Normal × ataque (`label`) | 0,9995 | **0,9993** | 0,9995 |
| Tipo de ataque (`type`) | 0,9951 | **0,9525** | 0,9950 |
| Predição do cluster (`cluster_kmeans30`) | 0,9144 | **0,7648** | 0,9265 |

A tarefa de prever os clusters apresentou o menor macro-F1, especialmente devido à dificuldade em grupos pouco representados no teste.

### Matriz de confusão — K-Means com 30 clusters

A figura abaixo é a **matriz original do experimento**, referente à **predição supervisionada de `cluster_kmeans30` no conjunto de teste**, e não uma matriz que relaciona diretamente os clusters às famílias de ataques.

![Matriz de confusão original de cluster_kmeans30](figuras/matriz-confusao-clusters-k30.png)

Embora o modelo de agrupamento tenha **30 clusters**, apenas **21 identificadores aparecem nas 10.984 amostras de teste**. A matriz apresenta as classes observadas, e o macro-F1 da tarefa foi **0,7648**.

[Análise da matriz e métricas por cluster](resultados/README.md#predição-dos-clusters-e-matriz-de-confusão) · [CSV original de contagens](resultados/matriz-confusao-clusters-k30-teste.csv) · [F1 por cluster](figuras/f1-por-cluster.png)

### Importância da separação por grupos

Na **predição de clusters**, a validação cruzada convencional obteve macro-F1 de **0,9993 ± 0,00039**, enquanto a validação cruzada por grupos obteve **0,7967 ± 0,1044**; no teste por grupos o macro-F1 foi **0,7648**. Essa diferença mostra que validações que não consideram conexões relacionadas podem superestimar o desempenho.

## Mais gráficos e resultados

O documento **[Resultados detalhados](resultados/README.md)** reúne:
- métricas completas de clustering e classificação em validação e teste;
- F1 por família de ataque e por cluster, com análise das classes menos representadas;
- matrizes de confusão, pureza, cobertura e comparação dos algoritmos;
- gráficos da seleção de `k` e tabelas CSV extraídas dos experimentos.

As [figuras disponíveis](figuras/README.md) foram copiadas diretamente dos arquivos originais do repositório SBCUP.

## Apresentação e pesquisa relacionada

**SIA UFV 2026 · Painel 187 · Espaço Multiuso · 21/10/2026, 10h30–12h.**

Este trabalho apresenta resultados experimentais de análise de tráfego, **sem implantação operacional de IDS em gateways de névoa**. As avaliações posteriores com uma população maior do TON_IoT não são tratadas aqui como parte do mesmo experimento.

- [SBCUP 2026 — implementação, notebooks e resultados originais](https://github.com/Math-BUG/iot-fog-ids-two-phase)
- [ERAD-SE 2026 — experimentos CPU/GPU](https://github.com/Math-BUG/experimento_erad)
- [Generalização de IDS — continuação da pesquisa](https://github.com/Math-BUG/ids_generalization_pipeline)

**Artigo relacionado:** PEREIRA, M. A. S.; SOUZA, V. B.; FERNANDES, D. L. *Abordagem em duas fases para detecção e classificação de ataques em redes IoT com computação em névoa*. SBCUP, 2026.
