# Figuras dos resultados

As figuras deste repositório foram retiradas diretamente dos artefatos da pesquisa apresentados no SBCUP 2026. Os arquivos de métricas originais, notebooks e demais imagens estão no [repositório técnico SBCUP](https://github.com/Math-BUG/iot-fog-ids-two-phase). Nenhum gráfico foi reconstruído a partir de CSV nesta transferência.

| Figura | O que representa | Arquivo original |
| --- | --- | --- |
| [Arquitetura em duas fases](arquitetura-duas-fases.png) | Diagrama da abordagem apresentada no artigo | Extraída do material do artigo |
| [F1 por classe](f1-por-classe.png) | Classificação supervisionada de `type` | `gráficos/pipeline/f1_por_classe_type.png` |
| [Matriz de confusão de tipo](matriz-confusao-tipo.png) | Classificação de `type` | `gráficos/pipeline/matriz_confusao_type.png` |
| [Pureza por cluster](pureza-por-cluster.png) | Composição dos agrupamentos K-Means | `gráficos/pipeline/kmeans30_pureza_por_cluster.png` |
| [**Matriz de confusão de clusters k=30**](matriz-confusao-clusters-k30.png) | Predição de `cluster_kmeans30` no teste (21 classes observadas) | `gráficos/pipeline/matriz_confusao_cluster_kmeans30.png` |
| [F1 por cluster](f1-por-cluster.png) | F1 de cada cluster previsto | `gráficos/pipeline/f1_por_classe_cluster_kmeans30.png` |
| [Tipos por cluster](tipos-por-cluster.png) | Distribuição de tipos de ataque entre clusters | `gráficos/pipeline/kmeans30_heatmap_type_por_cluster.png` |
| [Cobertura versus pureza](cobertura-pureza.png) | Cobertura dos grupos conforme o limiar de pureza | `gráficos/pipeline/kmeans30_cobertura_vs_limiar_pureza.png` |
| [Silhouette por k](silhueta-por-k.png) | Seleção exploratória de k | `gráficos/exploratório/kmeans_silhouette_por_k.png` |
| [AMI por k](ami-tipo-por-k.png) | Alinhamento exploratório com tipos de ataque | `gráficos/exploratório/kmeans_ami_type_por_k.png` |
| [Comparação de algoritmos](comparativo-agrupamentos.png) | Exploração K-Means, DBSCAN e hierárquico | `gráficos/exploratório/comparativo_kmeans_dbscan_hierarquico.png` |

As curvas exploratórias representam a **etapa de seleção**, enquanto as matrizes e métricas em [resultados](../resultados/README.md) descrevem as avaliações do pipeline final. A matriz de confusão de clusters **não deve ser interpretada como matriz de confusão entre famílias de ataques**.
