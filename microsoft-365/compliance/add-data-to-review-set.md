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
description: Saiba como adicionar resultados de pesquisa ou exemplos desses resultados de pesquisa a um conjunto de Advanced eDiscovery de análise de caso.
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919973"
---
# <a name="add-search-results-to-a-review-set"></a>Adicionar os resultados da pesquisa a um conjunto de revisão

Quando você estiver satisfeito com os resultados de uma pesquisa e estiver pronto para revisar e analisar os resultados da pesquisa, poderá adicioná-los a um conjunto de revisão no caso. Copiar os dados originais para o conjunto de revisão também facilita o processo de revisão e análise, fornecendo ferramentas de análise avançadas, como detecção de temas, detecção quase duplicada e identificação de thread de email. Você também pode adicionar dados de fontes de dados que não Microsoft 365 dados a um conjunto de revisão para que você possa revisar esses dados, além dos dados coletados do Microsoft 365.

Quando você adiciona os resultados de uma pesquisa a um conjunto de  revisão (os conjuntos de revisão em um caso são listados na guia Conjuntos de revisão), as seguintes coisas ocorrem:

- A pesquisa é executado novamente. Isso significa que os resultados reais da pesquisa copiados para o conjunto de revisão podem ser diferentes dos resultados estimados que foram retornados quando a pesquisa foi executado pela última vez.

- Todos os itens nos resultados da pesquisa são copiados da fonte de dados original nos serviços ao vivo e copiados para um local seguro do Azure Armazenamento na nuvem da Microsoft.

- Todos os itens (incluindo o conteúdo e os metadados) são reindexados para que todos os dados no conjunto de revisão sejam totalmente pesquisáveis durante a revisão dos dados de caso. A reindexação dos dados resulta em pesquisas completas e rápidas quando você pesquisa os dados no conjunto de revisão durante a investigação de caso.

- Um arquivo criptografado com uma tecnologia de criptografia [da Microsoft](encryption.md) e anexado a uma mensagem de email retornada nos resultados da pesquisa é descriptografado quando a mensagem de email e o arquivo anexado são adicionados ao conjunto de revisão. Você pode revisar e consultar o arquivo descriptografado no conjunto de revisão. Você precisa receber a função de descriptografia RMS para adicionar anexos de email descriptografados a um conjunto de revisão. Para obter mais informações, consulte [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).

Para adicionar dados a um conjunto de  revisão, clique em uma pesquisa na guia Pesquisas e clique em Adicionar resultados para revisar **o conjunto** na página de sobrevoo.

Você pode adicionar a um conjunto de revisão existente ou criar um novo conjunto de revisão.  Se adicionar a um novo conjunto de revisão, especifique o nome e clique em **Adicionar** para exibir a página de sobrevoo.

![Selecione um conjunto de revisão e configure opções de coleção](../media/AeD_AddToReviewSet.png)

Adicionar dados a um conjunto de revisão é um processo de execução longa. Esse processo inclui a coleta de itens das fontes de dados originais no Microsoft 365 (por exemplo, de caixas de correio e sites), copiá-los para o local do Azure Armazenamento (esse processo de cópia também é chamado de *ingestão*) e, em seguida, reindexar os itens. Você pode acompanhar o progresso na  guia **Trabalhos** ou na guia Pesquisas monitorando o status na coluna Dados adicionados para revisar **o conjunto de** tarefas. Depois que o processamento do conjunto  de revisão for concluído, clique na guia Revisar conjuntos no caso e clique no conjunto de revisão para iniciar o processo de filtragem, revisão, marcação e exportação de dados no conjunto de revisão.

## <a name="define-options-to-scope-your-collection-for-review"></a>Definir opções para escopo de sua coleção para revisão

Quando você adiciona o conteúdo de uma pesquisa a um conjunto de revisão existente ou novo, você tem as seguintes opções para coletar o conteúdo para revisão:

- **Incluir versões SharePoint (beta)**: Use essa opção para habilitar a coleção de todas as versões de um documento SharePoint de acordo com os limites de versão e os parâmetros de pesquisa da coleção. Selecionar essa opção aumentará significativamente o tamanho dos itens adicionados ao conjunto de revisão.

- **Opções de recuperação de** conversa : Os itens adicionados ao conjunto de revisão são habilitados para conversas encadeadas para ajudar a revisar o conteúdo no contexto da conversa de ida e volta. Para obter mais informações, [consulte Review conversations in Advanced eDiscovery](conversation-review-sets.md).

- **Habilitar a recuperação para anexos** modernos: use essa opção para incluir anexos modernos ou arquivos vinculados na coleção para revisão posterior. Para obter mais informações sobre as propriedades pesquisáveis relacionadas a anexos modernos, consulte [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

## <a name="add-a-sample-to-a-review-set"></a>Adicionar um exemplo a um conjunto de revisão

Se você quiser validar os resultados de uma pesquisa mais detalhadamente antes de adicioná-los a um conjunto de revisão, adicione um exemplo dos resultados da pesquisa a um conjunto de revisão em vez de adicionar tudo.

Para adicionar um exemplo a um conjunto  de revisão, clique em uma pesquisa na guia Pesquisas e clique em **Exemplo** na página de sobrevoo. Na página **Parâmetros de amostragem,** escolha uma das seguintes opções:

- **Nível de confiança %** e **intervalo de** confiança % - Os itens adicionados ao conjunto de revisão serão determinados pelos parâmetros estatísticos que você definir. Se você normalmente usar um nível de confiança e um intervalo durante a amostragem de resultados, especifique-os nas caixas de seleção. Caso contrário, use as configurações padrão.

- **Amostra aleatória %** - Os itens adicionados ao conjunto de revisão se baseiam em uma seleção aleatória da porcentagem especificada do número total de itens retornados pela pesquisa.

Depois de selecionar e configurar uma das opções anteriores, escolha um conjunto de revisão para adicionar o exemplo e clique em **Enviar**. Novamente, você pode acompanhar o progresso na  guia **Trabalhos** ou na guia Pesquisas monitorando o status na coluna Dados adicionados para revisar **o conjunto** de tarefas.

## <a name="optical-character-recognition"></a>Reconhecimento óptico de caracteres

Quando você adiciona resultados de pesquisa a um conjunto de revisão, a funcionalidade de reconhecimento óptico de caracteres (OCR) no Advanced eDiscovery extrai automaticamente o texto de imagens e inclui o texto da imagem com os dados adicionados a um conjunto de revisão. Você pode exibir o texto extraído no visualizador de texto do arquivo de imagem selecionado no conjunto de revisão. Isso permite revisar e analisar com mais detalhes o texto nas imagens. OCR é compatível com arquivos soltos, anexos de email e imagens incorporadas. Para ver a lista de formatos de arquivo de imagem compatíveis com OCR, confira [Tipos de arquivos compatíveis com a Descoberta Eletrônica Avançada](supported-filetypes-ediscovery20.md#image).

Você deve habilitar a funcionalidade OCR em cada caso que criar na Descoberta Eletrônica Avançada. Para obter mais informações, consulte [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).
