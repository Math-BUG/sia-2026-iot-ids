# Checklist — revisão do painel para o SIA 2026

Este checklist se refere ao trabalho **24615**, baseado no resumo aprovado no SIA.

- [ ] Manter o título exatamente como aprovado: **Arquitetura híbrida para detecção de tráfego malicioso em ambientes IoT**.
- [ ] Declarar corretamente as partições `train=183.158`, `val=16.901`, `test=10.984`.
- [ ] Descrever ausência de interseção da **chave composta** `src_ip|dst_ip|service|proto`; isso **não prova** que cada IP individual é exclusivo de uma partição.
- [ ] Indicar que a CV convencional e a CV por grupos (`0,9993` vs. `0,7967`) são da **predição dos clusters**.
- [ ] Descrever a computação em névoa como contexto/proposta arquitetural, não como gateway já implantado e avaliado.
- [ ] Identificar a classe MITM com apenas 1.043 observações (0,49%), evitando conclusões sobre todos os cenários MITM.
- [ ] Conferir quais logotipos de apoio financeiro são justificados. O cadastro fornecido indica **CNPq**; CAPES/FAPEMIG não devem constar sem confirmação de apoio.
- [ ] Conferir legibilidade dos blocos a pelo menos 1 metro, conforme orientação do SIA.
- [ ] Utilizar até cinco referências e identificar autores, orientador, instituição, categoria e ODS 9.
- [ ] Conferir PDF e PPTX entre si antes de declarar ambos versões finais.
- [ ] Após apresentação, arquivar o painel efetivamente usado e indicar data/versão.

Não publicar **relatório final assinado**, fichas cadastrais nem dados pessoais administrativos.
