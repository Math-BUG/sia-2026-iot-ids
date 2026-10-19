# Apresentação em painel — SIA UFV 2026

**Trabalho nº 24615:** *Arquitetura híbrida para detecção de tráfego malicioso em ambientes IoT*.

Apresentação **programada** para **21/10/2026, de 10h30 a 12h**, no **Espaço Multiuso**, painel **187**. Dimensões: **90 × 120 cm**, orientação vertical, conforme o [modelo oficial do SIA](https://sia.ufv.br/apresentacao-painel/).

## Arquivos já disponíveis

| Arquivo | Descrição | Estado |
| --- | --- | --- |
| [`painel-em-revisao.pdf`](painel-em-revisao.pdf) | Painel em PDF para conferência visual | **Rascunho para revisão** |
| [`painel-editavel-revisar.pptx`](painel-editavel-revisar.pptx) | Versão PowerPoint editável | **Rascunho para revisão** |
| [`visualizacao-painel.png`](visualizacao-painel.png) | Imagem de prévia | **Prévia** |

Os três arquivos foram enviados ao repositório. **Não são identificados como versão final apresentada.** O PDF e o PowerPoint devem ser comparados antes da impressão: não foi confirmada equivalência entre os conteúdos das duas versões.

## Revisões ainda recomendadas

- No painel, substituir *“partições independentes por IPs, serviço e protocolo”* por uma descrição fiel do critério de **chave composta** `src_ip|dst_ip|service|proto`. O protocolo evita repetição dessa combinação, não necessariamente de cada IP isolado.
- Indicar explicitamente que **CV comum = 0,9993** e **CV por grupos = 0,7967** correspondem à **predição dos clusters**, não à classificação binária.
- Garantir que computação em névoa seja apresentada como **contexto arquitetural/proposta**, sem atribuir implantação real em gateways ao estudo.
- Conferir fonte e leitura a 1 metro, de acordo com as normas.
- O cadastro informado registra apoio **CNPq**; outros financiadores só devem ser exibidos se houver confirmação documental.

Consulte a lista completa em [`docs/verificacao.md`](../docs/verificacao.md).

A execução científica, tabelas e métricas originais pertencem ao [repositório do artigo SBCUP](https://github.com/Math-BUG/iot-fog-ids-two-phase).