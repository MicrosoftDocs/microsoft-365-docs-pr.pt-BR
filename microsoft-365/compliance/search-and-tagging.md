---
title: Pesquisa e marcação
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: Na descoberta eletrônica avançada, o módulo de pesquisa e marcação permite pesquisar, Visualizar e organizar os documentos em seu caso. Atualmente, este módulo está no beta.
ms.openlocfilehash: a3597cf0abad7095de7a7c6857052f269d202598
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081389"
---
# <a name="search-and-tagging"></a>Pesquisa e marcação

Na descoberta eletrônica avançada, o módulo de pesquisa e marcação permite pesquisar, Visualizar e organizar os documentos em seu caso. Atualmente, este módulo está no beta. Para obter uma breve demonstração de pesquisa e marcação, confira o botão [gerenciar seus dados com vídeo de descoberta eletrônica avançada](https://www.youtube.com/watch?v=VaPYL3DHP6I) .

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="search-the-documents-in-your-case"></a>Pesquisar os documentos no seu caso

Depois de processar documentos em um caso de descoberta eletrônica avançada (e, opcionalmente, executar o módulo de análise ou relevância), você pode usar a pesquisa e marcação para pesquisar documentos e organizá-los aplicando marcas específicas de maiúsculas e minúsculas (também chamados de rótulos). Você pode definir uma consulta de pesquisa usando os cartões de condição fornecidos ou usando um idioma de consulta semelhante ao KQL no cartão de condição de palavras-chave. A sintaxe KQL comum, como e, ou, não e NEAR (n), é suportada, assim como um curinga de vários caracteres à direita (*). 

A tabela a seguir lista as propriedades que você pode pesquisar usando uma consulta de palavra-chave KQL. Como alternativa, você pode usar um cartão de condição para na ferramenta de pesquisa de descoberta eletrônica avançada para adicionar uma condição (para propriedades selecionadas) a uma consulta de pesquisa.

|**Propriedade**|**Descrição**|
|:-----|:-----|
|**caselabel** <br/> | O nome da marca criada/aplicada quando um documento é marcado. <br/> |
|**custódia** <br/> | Os responsáveis associados a um documento; sujeito a limitações. <br/> |
|**data** <br/> | Data de envio de email; a data de modificação para documentos de site. <br/> |
|**FileID** <br/> | A ID do arquivo no caso. <br/> |
|**filetype** <br/> | A extensão de arquivo nativo. <br/> |
|**fileclass** <br/> | Email, documento ou anexo. <br/> |
|**senderauthor** <br/> | O remetente de email; o autor para documentos de site. <br/> |
|**size** <br/> | O tamanho do arquivo em KB. <br/> |
|**subjecttitle** <br/> | O assunto de email; o título dos documentos do site. <br/> |
|**bcc** <br/> | O campo Cco de um email. <br/> |
|**cc** <br/> | O campo CC de um email. <br/> |
|**participants** <br/> | O endereço de email de todos os participantes de um thread de email, incluindo links ausentes. <br/> |
|**received** <br/> | A data em que um email foi recebido. <br/> |
|**recipients** <br/> | Destinatários de um email, incluídos nos campos para, CC ou Cco. <br/> |
|**sender** <br/> | O remetente de um email. <br/> |
|**lastmodifieddate** <br/> | A data da última modificação de um documento de site. <br/> |
|**sent** <br/> | A data de envio de um email. <br/> |
|**to** <br/> | O destinatário listado no campo para de um email. <br/> |
|**autor** <br/> | O autor de um documento de site. <br/> |
|**title** <br/> | O título de um documento de site. <br/> |
|**dominanttheme**\* <br/> | O tema dominante de um item. <br/> |
|**themelist**\* <br/> | Temas associados a um item. <br/> |
|**readpercentile_ [issuenum]**\*\* <br/> | O percentil de leitura de um item, para o problema definido por [issuenum]. <br/> |
|**relevancescore_ [issuenum]**\*\* <br/> | A pontuação de relevância de um item, para o problema definido por [issuenum]. <br/> |
|**relevancetag_ [TagName]**\*\* <br/> | Se um item tiver sido marcado manualmente para relevância, a marca definida por [TagName]. <br/> |
|||

\*Disponível somente se o módulo de temas tiver sido executado.

\*\*Disponível somente se o módulo de relevância tiver sido executado.

Como alternativa, você pode usar um cartão de condição na ferramenta de pesquisa de descoberta eletrônica avançada para adicionar uma condição (para propriedades selecionadas) a uma consulta de pesquisa. A captura de tela a seguir mostra as condições que podem ser adicionadas a uma consulta. A coluna **grupo** indica se a propriedade se aplica a emails, documentos de site ou ambos (indicados pelo valor *comum*). Essa coluna também identifica as propriedades pesquisáveis que estão disponíveis após a execução do módulo de relevância.

![Condições de pesquisa na ferramenta de pesquisa de descoberta eletrônica avançada](../media/AeDSearchConditions.png)

Para obter mais informações sobre propriedades pesquisáveis, consulte [keyword queries and Search Conditions](keyword-queries-and-search-conditions.md).
  
## <a name="see-also"></a>Confira também

[Descoberta Eletrônica Avançada do Office 365](office-365-advanced-ediscovery.md)
  
[Noções básicas sobre avaliação em relevância](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Marcação e avaliação](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Treinamento de marcação e relevância](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análise de relevância de rastreamento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidindo com base nos resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testando análise de relevância](test-relevance-analysis-in-advanced-ediscovery.md)

