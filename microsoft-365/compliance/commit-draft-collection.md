---
title: Commit a draft collection to a review set
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Depois de criar e iterar em um conjunto de rascunhos, você pode confirma-lo em um conjunto de revisão. Quando você confirma um conjunto de rascunhos, os itens coletados são adicionados ao conjunto de revisão no caso. Depois que os itens coletados estão no conjunto de revisão, você pode analisar, revisar e exportá-los.
ms.openlocfilehash: e28592e7aac289bfc0cc29d312963fa21d9f8fd4
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838825"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery"></a>Commit a draft collection to a review set in Advanced eDiscovery

Quando você estiver satisfeito com os itens coletados em uma coleção de rascunho e estiver pronto para analisar, marcar e revisá-los, você pode adicionar uma coleção a um conjunto de revisão no caso. Quando você confirma um conjunto de rascunhos em um conjunto de revisão, os itens coletados são copiados de seu local de conteúdo original no Microsoft 365 para um conjunto de revisão. Um conjunto de revisão é um local de Armazenamento do Azure fornecido pela Microsoft na nuvem da Microsoft.

## <a name="commit-a-draft-collection-to-a-review-set"></a>Commit a draft collection to a review set

1. No Centro de conformidade do Microsoft 365, abra o caso  Descoberta Avançada e selecione a guia Coleções para exibir uma lista das coleções no caso.

   ![Lista de coleções em um caso](../media/CommitDraftCollections1.png)

   > [!TIP]
   > Um valor de `Estimated` na coluna **Status** identifica as coleções de rascunho que podem ser adicionadas a um conjunto de revisão. Um status indica `Committed` que uma coleção já foi adicionada a um conjunto de revisão.

2. Na página **Coleções,** selecione o conjunto de rascunhos que você deseja comprometer com um conjunto de revisão.

3. Na parte inferior da página de sobrevoo, selecione **Actions**  >  **Edit collection**.

4. No assistente de edição do conjunto, clique **em Próximo** até que a página Salvar **rascunho ou** coletar seja exibida.

5. Defina as seguintes configurações:

   1. Selecione **Coletar itens e adicione ao conjunto de revisão**.

   2. Decida se deve adicionar a coleção a um novo conjunto de revisão (que é criado depois de enviar a coleção) ou a um conjunto de revisão existente. Conclua esta seção com base em sua decisão.

   3. Configure as configurações de coleção adicionais:

       - Mensagens do Teams e **do Yammer**: selecione essa opção para adicionar threads de conversa à coleção que incluem os itens de chat retornados pela consulta de pesquisa na coleção. Isso significa que a conversa de chat que contém itens que corresponderem aos critérios de pesquisa é reconstruída. Isso permite que você revise itens de chat no contexto da conversa de ida e volta. Para obter mais informações, consulte [Threading de conversa em Descoberta Avançada da Descoberta Pública.](conversation-review-sets.md)

       - **Anexos de nuvem**: selecione essa opção para incluir anexos modernos ou arquivos vinculados quando os resultados da coleção são adicionados ao conjunto de revisão. Isso significa que o arquivo de destino de um anexo moderno ou arquivo vinculado é adicionado ao conjunto de revisão.

       - **Versões do SharePoint**: selecione essa opção para habilitar a coleção de todas as versões de um documento do SharePoint de acordo com os limites de versão e os parâmetros de pesquisa da coleção. Selecionar essa opção aumentará significativamente o tamanho dos itens adicionados ao conjunto de revisão.

   4. Configure as configurações para definir a escala da coleção a ser acrescentada ao conjunto de revisão:

      - **Adicionar todos os resultados da coleção**: Selecione essa opção para adicionar todos os itens que corresponderem aos critérios de pesquisa da coleção ao conjunto de revisão.

      - **Adicione um exemplo dos resultados da** coleção : Selecione essa opção para adicionar um exemplo dos resultados da coleção ao conjunto de revisão em vez de adicionar todos os resultados. Se você selecionar essa opção, clique em **Editar parâmetros de exemplo** e escolha uma das seguintes opções:

         - **Exemplo com base na confiança**: os itens da coleção são adicionados ao conjunto de revisão serão determinados pelos parâmetros estatísticos que você definir. Se você normalmente usar um nível de confiança e um intervalo durante a amostragem de resultados, especifique-os nas caixas de seleção. Caso contrário, use as configurações padrão.

         - **Exemplo aleatório:** os itens da coleção são adicionados ao conjunto de revisão com base em uma seleção aleatória da porcentagem especificada do número total de itens retornados pela pesquisa.

6. Na página **Revisar sua coleção,** você pode revisar as configurações de coleção configuradas na página anterior. Clique **em Editar** se quiser alterá-los.

7. Clique **em Enviar** para criar o conjunto de rascunhos. Uma página é exibida confirmando que a coleção foi criada.

## <a name="what-happens-after-you-commit-a-draft-collection"></a>O que acontece depois que você confirma um conjunto de rascunhos

Quando você confirma um conjunto de rascunhos em um conjunto de revisão, as seguintes coisas ocorrem:

- A consulta de pesquisa de coleção é executado novamente. Isso significa que os resultados reais da pesquisa copiados para o conjunto de revisão podem ser diferentes dos resultados estimados que foram retornados quando a pesquisa da coleção foi executado pela última vez.

- Todos os itens nos resultados da pesquisa são copiados da fonte de dados original no serviço ao vivo e copiados para um local de Armazenamento seguro do Azure na nuvem da Microsoft.

- Todos os itens (incluindo o conteúdo e os metadados) que não estão localizados em fontes de dados custodiadas ou não custodiadas são reindexados (em um processo chamado indexação profunda *)* para que todos os dados no conjunto de revisão sejam totalmente pesquisáveis durante a revisão dos dados de caso. A reindexação do conteúdo em uma coleção resulta em pesquisas completas e rápidas quando você pesquisa ou filtra o conteúdo no conjunto de revisão durante a investigação de caso.

- Documentos criptografados do SharePoint e do OneDrive e arquivos criptografados anexados mensagens de email retornadas nos resultados da pesquisa são descriptografadas quando você confirma a coleção em um conjunto de revisão. Você pode revisar e consultar os arquivos descriptografados no conjunto de revisão. Para obter mais informações, consulte [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).

- A funcionalidade de reconhecimento óptico de caracteres (OCR) extrai texto de imagens e inclui o texto da imagem com o conteúdo adicionado a um conjunto de revisão. Para obter mais informações, consulte a seção [Reconhecimento óptico de](#optical-character-recognition) caracteres neste artigo.

- Depois que a confirmação for concluída com êxito, o valor da coluna de status da guia **Coleções** será alterado para `Committed` .

## <a name="optical-character-recognition"></a>Reconhecimento óptico de caracteres

Quando você confirma uma coleção em um conjunto de revisão, a funcionalidade de reconhecimento óptico de caracteres (OCR) na Descoberta Avançada extrai automaticamente o texto de imagens e inclui o texto da imagem com o conteúdo adicionado a um conjunto de revisão. Você pode exibir o texto extraído no visualizador de texto do arquivo de imagem selecionado no conjunto de revisão. Isso permite que você conduza mais análises e análises sobre o texto em imagens. O OCR é suportado para arquivos soltos, anexos de email e imagens incorporadas. Para ver uma lista de formatos de arquivo de imagem com suporte para OCR, consulte Tipos de arquivo com suporte [em Descoberta Avançada em Descoberta Eletrônico Avançada](supported-filetypes-ediscovery20.md#image).

Você precisa habilitar a funcionalidade OCR para cada caso criado na Descoberta Avançada. Para obter mais informações, consulte [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).
