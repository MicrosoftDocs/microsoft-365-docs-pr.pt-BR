---
title: Adicionar os resultados da pesquisa a um conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Saiba como adicionar resultados de pesquisa ou amostras desses resultados de pesquisa a um conjunto avançado de análise de casos de descoberta eletrônica.
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919973"
---
# <a name="add-search-results-to-a-review-set"></a>Adicionar os resultados da pesquisa a um conjunto de revisão

Quando estiver satisfeito com os resultados de uma pesquisa e estiver pronto para revisar e analisar os resultados da pesquisa, você poderá adicioná-los a uma análise definida no caso. Copiar os dados originais para o conjunto de revisão também facilita o processo de revisão e análise fornecendo ferramentas avançadas de análise, como detecção de temas, detecção de duplicidade próxima e identificação de thread de email. Você também pode adicionar dados de fontes de dados que não são da Microsoft 365 a um conjunto de revisão para que possa revisar os dados além dos dados que coleta da Microsoft 365.

Quando você adiciona os resultados de uma pesquisa a um conjunto de revisão (os conjuntos de revisão em um caso são listados na guia **conjuntos de revisão** ), ocorrem as seguintes ações:

- A pesquisa é executada novamente. Isso significa que os resultados de pesquisa reais copiados para o conjunto de revisão podem ser diferentes dos resultados estimados que foram retornados quando a pesquisa foi executada pela última vez.

- Todos os itens nos resultados da pesquisa são copiados da fonte de dados original nos serviços do Live e copiados para um local seguro de armazenamento do Azure na nuvem da Microsoft.

- Todos os itens (incluindo o conteúdo e os metadados) são reindexados para que todos os dados no conjunto de revisão sejam totalmente pesquisáveis durante a revisão dos dados de caso. A reindexação dos dados resulta em pesquisas completas e rápidas quando você pesquisa os dados na revisão definida durante a investigação do caso.

- Um arquivo criptografado com uma [tecnologia de criptografia da Microsoft](encryption.md) e é anexado a uma mensagem de email retornada nos resultados da pesquisa é descriptografado quando a mensagem de email e o arquivo anexado são adicionados ao conjunto de revisão. Você pode revisar e consultar o arquivo descriptografado no conjunto de revisão. Você precisa receber a função de descriptografia do RMS para adicionar anexos de email descriptografados a um conjunto de revisão. Para obter mais informações, consulte [descriptografia no Microsoft 365 eDiscovery Tools](ediscovery-decryption.md).

Para adicionar dados a um conjunto de revisão, clique em uma pesquisa na guia **pesquisas** e, em seguida, clique em **Adicionar resultados para revisão definida** na página do menu suspenso.

Você pode adicionar a um conjunto de revisão existente ou criar um novo conjunto de revisão.  Se estiver adicionando a um novo conjunto de revisão, especifique o nome e clique em **Adicionar** para exibir a página de menu suspenso.

![Selecionar um conjunto de análise e configurar opções de coleção](../media/AeD_AddToReviewSet.png)

A adição de dados a um conjunto de revisão é um processo de execução demorada. Esse processo inclui a coleta de itens das fontes de dados originais no Microsoft 365 (por exemplo, de caixas de correio e sites), copiando-os para o local de armazenamento do Azure (esse processo de cópia também é chamado de *inclusão* ) e, em seguida, reindexar os itens. Você pode acompanhar o progresso na guia **trabalhos** ou na guia **pesquisas** monitorando o status na coluna **Adicionar dados para revisão** . Depois que o processamento do conjunto de revisão estiver concluído, clique na guia **revisar conjuntos** no caso e, em seguida, clique no conjunto de revisão para iniciar o processo de filtragem, revisão, marcação e exportação de dados no conjunto de revisão.

## <a name="define-options-to-scope-your-collection-for-review"></a>Definir opções para fazer o escopo da sua coleção para revisão

Ao adicionar o conteúdo de uma pesquisa a um conjunto de revisão novo ou existente, você tem as seguintes opções de como coletar o conteúdo para revisão:

- **Incluir versões do SharePoint (beta)** : Use esta opção para habilitar a coleção de todas as versões de um documento do SharePoint por limites de versão e parâmetros de pesquisa da coleção. Selecionar essa opção aumentará significativamente o tamanho dos itens que são adicionados ao conjunto de revisão.

- **Opções de recuperação de conversa** : os itens adicionados ao conjunto de revisão estão habilitados para conversas encadeadas para ajudar a revisar o conteúdo no contexto da conversa de trás e para frente. Para obter mais informações, consulte [revisar conversas na descoberta eletrônica avançada](conversation-review-sets.md).

- **Habilitar recuperação para anexos modernos** : Use esta opção para incluir anexos modernos ou arquivos vinculados na coleção para análise adicional. Para obter mais informações sobre as propriedades pesquisáveis relacionadas a anexos modernos, consulte [documentar campos de metadados na descoberta eletrônica avançada](document-metadata-fields-in-Advanced-eDiscovery.md).

## <a name="add-a-sample-to-a-review-set"></a>Adicionar um exemplo a um conjunto de revisão

Se você quiser validar os resultados de uma pesquisa com mais detalhes antes de adicionar todos eles a um conjunto de revisão, você pode adicionar um exemplo dos resultados da pesquisa a um conjunto de revisão, em vez de adicionar tudo.

Para adicionar um exemplo a um conjunto de revisão, clique em uma pesquisa na guia **pesquisas** e clique em **amostra** na página do menu suspenso. Na página **parâmetros de amostragem** , escolha uma das seguintes opções:

- O **nível de confiança%** e o **intervalo de confiança%** -os itens adicionados ao conjunto de revisão serão determinados pelos parâmetros estatísticos definidos. Se você costuma usar um nível de confiança e um intervalo ao obter resultados de amostragem, especifique-os nas caixas suspensas. Caso contrário, use as configurações padrão.

- **Amostra aleatória%** -os itens adicionados ao conjunto de revisão são baseados em uma seleção aleatória do percentual especificado do número total de itens retornados pela pesquisa.

Após selecionar e configurar uma das opções anteriores, escolha um conjunto de revisão para adicionar o exemplo a e clique em **Enviar**. Novamente, você pode acompanhar o progresso na guia **trabalhos** ou na guia **pesquisas** monitorando o status na coluna **Adicionar dados para revisão** .

## <a name="optical-character-recognition"></a>Reconhecimento óptico de caracteres

Quando você adiciona resultados de pesquisa a um conjunto de revisão, a funcionalidade de reconhecimento óptico de caracteres (OCR) em descoberta eletrônica avançada extrai automaticamente o texto de imagens e inclui o texto da imagem com os dados que são adicionados a um conjunto de revisão. Você pode exibir o texto extraído no Visualizador de texto do arquivo de imagem selecionado no conjunto de revisão. Isso permite que você realize análises e análises adicionais sobre texto em imagens. O OCR tem suporte para arquivos soltos, anexos de email e imagens incorporadas. Para obter uma lista de formatos de arquivo de imagem suportados para OCR, confira [tipos de arquivo com suporte na descoberta eletrônica avançada](supported-filetypes-ediscovery20.md#image).

Você precisa habilitar a funcionalidade de OCR para cada caso que você criar na descoberta eletrônica avançada. Para obter mais informações, consulte [Configurar definições de pesquisa e análise](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).
