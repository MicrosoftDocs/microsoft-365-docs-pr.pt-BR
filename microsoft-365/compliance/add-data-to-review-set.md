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
description: Saiba como adicionar resultados de pesquisa ou exemplos desses resultados de pesquisa a um conjunto de revisão de caso de Descoberta Avançada.
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919973"
---
# <a name="add-search-results-to-a-review-set"></a>Adicionar os resultados da pesquisa a um conjunto de revisão

Quando você estiver satisfeito com os resultados de uma pesquisa e estiver pronto para revisar e analisar esses resultados de pesquisa, poderá adicioná-los a um conjunto de revisão no caso. Copiar os dados originais para o conjunto de revisão também facilita o processo de análise e revisão, fornecendo ferramentas avançadas de análise, como detecção de temas, detecção quase duplicada e identificação de thread de email. Você também pode adicionar dados de fontes de dados que não são do Microsoft 365 a um conjunto de revisão para que possa revisar esses dados, além dos dados que coleta do Microsoft 365.

Quando você adiciona os resultados de uma pesquisa a um conjunto de  revisão (os conjuntos de revisão em um caso são listados na guia Conjuntos de revisão), ocorrem as seguintes coisas:

- A pesquisa é executado novamente. Isso significa que os resultados reais da pesquisa copiados para o conjunto de revisão podem ser diferentes dos resultados estimados que foram retornados quando a pesquisa foi executado pela última vez.

- Todos os itens nos resultados da pesquisa são copiados da fonte de dados original nos serviços ao vivo e copiados para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

- Todos os itens (incluindo o conteúdo e os metadados) são reindexados para que todos os dados no conjunto de revisão sejam totalmente pesquisáveis durante a revisão dos dados de caso. A reindexação dos dados resulta em pesquisas completas e rápidas quando você pesquisa os dados no conjunto de revisão durante a investigação de caso.

- Um arquivo criptografado com uma tecnologia de criptografia da [Microsoft](encryption.md) e anexado a uma mensagem de email retornada nos resultados da pesquisa é descriptografado quando a mensagem de email e o arquivo anexado são adicionados ao conjunto de revisão. Você pode revisar e consultar o arquivo descriptografado no conjunto de revisão. Você precisa ter a função de descriptografar RMS para adicionar anexos de email descriptografados a um conjunto de revisão. Para obter mais informações, consulte [Descriptografia nas ferramentas de Descoberta eDiscovery do Microsoft 365.](ediscovery-decryption.md)

Para adicionar dados a um conjunto de  revisão, clique em uma pesquisa na guia Pesquisas e, em seguida, clique em Adicionar resultados para revisar o conjunto **na** página do flyout.

Você pode adicionar a um conjunto de revisão existente ou criar um novo conjunto de revisão.  Se estiver adicionando a um novo conjunto de revisão, especifique o nome e clique **em Adicionar** para exibir a página do flyout.

![Selecionar um conjunto de revisão e configurar opções de coleção](../media/AeD_AddToReviewSet.png)

Adicionar dados a um conjunto de revisão é um processo de longa execução. Esse processo inclui reunir itens das fontes de dados originais no Microsoft 365 (por exemplo, de caixas de correio e sites), copiá-los para o local de Armazenamento do Azure (esse processo de cópia também é chamado *de ingestão)* e reindexar os itens. Você pode acompanhar o progresso na  guia **Trabalhos** ou na guia Pesquisas monitorando o status na coluna Dados adicionados para **revisar o conjunto.** Depois que o processamento do conjunto  de revisão for concluído, clique na guia Conjuntos de revisão no caso e clique no conjunto de revisão para iniciar o processo de filtragem, revisão, marcação e exportação de dados no conjunto de revisão.

## <a name="define-options-to-scope-your-collection-for-review"></a>Definir opções para definir o escopo de sua coleção para revisão

Ao adicionar o conteúdo de uma pesquisa a um conjunto de revisão existente ou novo, você tem as seguintes opções de como coletar o conteúdo para revisão:

- **Incluir versões do SharePoint (beta)**: use essa opção para habilitar o conjunto de todas as versões de um documento do SharePoint de acordo com os limites de versão e os parâmetros de pesquisa do conjunto. Selecionar essa opção aumentará significativamente o tamanho dos itens adicionados ao conjunto de revisão.

- **Opções de recuperação de** conversa: os itens adicionados ao conjunto de revisão são habilitados para conversas encadeadas para ajudar a revisar o conteúdo no contexto da conversa de ida e volta. Para obter mais informações, [consulte Review conversations in Advanced eDiscovery](conversation-review-sets.md).

- **Habilitar a recuperação para anexos modernos:** use essa opção para incluir anexos modernos ou arquivos vinculados na coleção para revisão posterior. Para obter mais informações sobre as propriedades pesquisáveis relacionadas a anexos modernos, consulte Campos de metadados do [documento na Descoberta Avançada.](document-metadata-fields-in-Advanced-eDiscovery.md)

## <a name="add-a-sample-to-a-review-set"></a>Adicionar um exemplo a um conjunto de revisão

Se você deseja validar os resultados de uma pesquisa mais detalhadamente antes de adicionar todos eles a um conjunto de revisão, você pode adicionar um exemplo dos resultados da pesquisa a um conjunto de revisão em vez de adicionar tudo.

Para adicionar um exemplo a um conjunto de revisão, clique em uma pesquisa na guia **Pesquisas** e clique em **Exemplo** na página do flyout. Na página **Parâmetros de amostragem,** escolha uma das seguintes opções:

- **% de nível** de confiança e % de confiança **-** Os itens adicionados ao conjunto de revisão serão determinados pelos parâmetros estatísticos que você definir. Se você normalmente usa um nível de confiança e um intervalo durante a amostragem dos resultados, especifique-os nas caixas de lista. Caso contrário, use as configurações padrão.

- **Amostra aleatória %** - Os itens adicionados ao conjunto de revisão baseia-se em uma seleção aleatória da porcentagem especificada do número total de itens retornados pela pesquisa.

Depois de selecionar e configurar uma das opções anteriores, escolha um conjunto de revisão para adicionar o exemplo e clique em **Enviar.** Novamente, você pode controlar  o progresso na  guia Trabalhos ou na guia Pesquisas monitorando o status na coluna Dados adicionados para revisar **o conjunto.**

## <a name="optical-character-recognition"></a>Reconhecimento óptico de caracteres

Quando você adiciona resultados de pesquisa a um conjunto de revisão, a funcionalidade de reconhecimento óptico de caracteres (OCR) na Descoberta Automática extrai automaticamente o texto das imagens e inclui o texto da imagem com os dados adicionados a um conjunto de revisão. Você pode exibir o texto extraído no Visualizador de texto do arquivo de imagem selecionado no conjunto de revisão. Isso permite que você conduza análises e análises posteriores sobre texto em imagens. Há suporte para OCR para arquivos soltos, anexos de email e imagens incorporadas. Para uma lista de formatos de arquivo de imagem com suporte para OCR, consulte Tipos de arquivo com suporte na [Descoberta Eletrônico Avançada.](supported-filetypes-ediscovery20.md#image)

Você precisa habilitar a funcionalidade OCR para cada caso criado na Descoberta Avançada. Para obter mais informações, consulte [Definir configurações de pesquisa e análise.](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)
