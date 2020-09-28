---
title: Aproveitar a taxonomia do repositório de termos ao criar um extrator
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Aproveitar a taxonomia do repositório de termos ao criar um extrator em seu documento entendendo o modelo no Microsoft SharePoint Syntex.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295712"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Aproveitar a taxonomia do repositório de termos ao criar um extrator


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Ao criar um extrator em seu documento entendendo o modelo no SharePoint Syntex, você pode aproveitar a taxonomia do repositório de termos [dos serviços de metadados gerenciados](https://docs.microsoft.com/sharepoint/managed-metadata#terms) para exibir os termos preferenciais dos dados extraídos.  

Por exemplo, o modelo identifica e classifica todos os documentos de **contrato** que são carregados na biblioteca de documentos.  Além disso, o modelo também extrai um valor de **serviço de contrato** de cada contrato e o exibirá em uma coluna no modo de exibição de biblioteca. Entre os vários valores de serviços de contrato nos contratos, há vários valores mais antigos que sua empresa não usa mais e foi renomeado. Por exemplo, todas as referências aos termos *design*, *elementos gráficos*ou serviços de contrato *topografia* agora devem ser chamadas de *criativo*. Sempre que seu modelo extrai um dos termos desatualizados de um documento de contrato, você deseja que ele exiba o termo atual-criativo-no modo de exibição de biblioteca. No exemplo abaixo, ao treinar o modelo, vemos que um documento de exemplo contém o termo de *design*desatualizado.

   ![Repositório de termos](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a>Sinônimos de conjunto de termos 

Os conjuntos de termos são configurados no repositório de termos de serviços de metadados gerenciados no centro de administração do SharePoint. No exemplo abaixo, o [conjunto de termos](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) *dos serviços de contrato* é configurado para incluir vários termos, incluindo *criativo*.  Os detalhes de ti mostram que o termo tem três sinônimos (*design*, *elementos gráficos*e *topografia*) e que os sinônimos devem ser traduzidos para *criativo*.

   ![Conjunto de termos](../media/content-understanding/term-store.png)</br>

<Mike, aqui está onde não tenho certeza sobre como descrever isso.  Qual ação diz ao modelo que quando crio um extrator para extrair e exibir uma coluna de serviços de contrato, como essa coluna "marcada" para usar o conjunto de termos de metadados gerenciados para serviços de criação? >

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a>Configurar a coluna de site de biblioteca de documentos para um campo de metadados gerenciados


   ![Criar metadados gerenciados](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a>Confira também
[Introdução aos metadados gerenciados](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[Criar um extrator](create-an-extractor.md)</br>
[Criar uma coluna de metadados gerenciados](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





