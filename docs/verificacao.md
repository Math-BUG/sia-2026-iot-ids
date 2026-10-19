# Checklist de revisão — SIA 2026

Este repositório é **público**. O autor confirmou a versão final do painel em 19/10/2026, mas seu PDF ainda aguarda upload ao repositório. Os arquivos de apresentação já versionados são revisões anteriores. Veja [versão final](versao-final.md).

## Identificação e publicação

- [x] Título coincide com o resumo aprovado: **Arquitetura híbrida para detecção de tráfego malicioso em ambientes IoT**.
- [x] Trabalho 24615, Universidade Federal de Viçosa, modalidade Pesquisa — Graduação, ODS 9.
- [x] Autor e orientador identificados.
- [x] Painel PDF, PowerPoint editável e prévia enviados ao GitHub.
- [x] Resumo aprovado integralmente documentado.
- [x] Nenhum relatório assinado, ficha cadastral ou certificado individual entre os arquivos versionados nesta revisão.

## Verificações científicas pendentes no painel

- [x] **No PDF final fornecido pelo autor, a descrição da divisão por grupos foi corrigida:** o conjunto usa a chave composta `src_ip|dst_ip|service|proto`, sem sobreposição de grupos; não há garantia de exclusividade de cada IP isolado entre partições. O PDF disponível ainda usa *“partições independentes por IPs, serviço e protocolo”*.
- [x] O PDF final diferencia claramente a **macro-F1 de 0,9993 da classificação binária** da **macro-F1 de 0,9993 na CV convencional para predição dos clusters**.
- [x] O PDF final contextualiza MITM como classe rara (1.043 amostras; 0,49%), sem generalizações indevidas.
- [x] O PDF final mantém o caráter **experimental** da abordagem de névoa: sem implantação operacional em gateway ou medição de latência fim a fim.

## Revisão visual e institucional pendente

- [ ] Conferir leitura a 1 metro; o SIA recomenda Calibri tamanho 36, mas alguns blocos usam fonte menor.
- [ ] Conferir que **PDF e PPTX apresentam a mesma versão** e que a prévia corresponde à versão selecionada.
- [ ] Confirmar apoio financeiro. O cadastro fornecido registra **CNPq**; não atribuir CAPES ou FAPEMIG sem documentação.
- [ ] Conferir referências (até cinco), figuras e versão final autorizada antes da impressão.
- [ ] Após a sessão de 21/10/2026, arquivar separadamente o painel **efetivamente apresentado**, caso autorizado.

## Privacidade, dados e licença

- Os e-mails que aparecem no painel são **institucionais** e integram a identificação exigida para autores e orientador.
- Não acrescentar documentos com assinaturas, dados administrativos, certificados pessoais nem datasets brutos.
- Não presumir que um repositório público autoriza automaticamente a republicação de artigos, logotipos ou elementos do template por terceiros.

## Estado final de publicação

- [x] PDF final escolhido pelo autor, com CNPq e QR code verificados.
- [ ] Publicar o **arquivo PDF exato** em `apresentacao/painel-final-sia-2026.pdf`.
- [ ] Após upload, atualizar os links do README e conferir hash SHA-256.
