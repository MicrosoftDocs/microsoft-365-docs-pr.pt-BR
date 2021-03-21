---
title: Usar a Pesquisa da Microsoft para encontrar tópicos em Tópicos do Microsoft Viva
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Saiba como pesquisar tópicos no Microsoft Viva.
ms.openlocfilehash: 1739923c95b42f192bb2e285245f72c3e09e1c30
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925923"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Usar a Pesquisa da Microsoft para encontrar tópicos em Tópicos do Microsoft Viva

Embora os usuários do Viva Topics possam encontrar tópicos por meio de destaques de tópicos em seus sites do SharePoint, eles também podem encontrá-los por meio da Pesquisa da Microsoft. 

## <a name="topic-answer"></a>Resposta de tópico

Quando você pesquisa um tópico específico na Pesquisa da Microsoft (por exemplo, "Saturno"), se um tópico existir e for encontrado, ele exibirá o resultado no formato de sugestão Respostas.

A resposta do tópico será exibida:
- Nome do tópico
- Nomes alternativos: nomes alternativos ou acrônimos para o tópico.
- Definição: Descrição do tópico fornecido pela AI ou adicionado manualmente por uma pessoa.
- Pessoas sugeridas ou fixadas: pessoas sugeridas por AI ou fixadas ao tópico por uma pessoa
- Recursos sugeridos ou fixados: arquivos, páginas ou sites sugeridos por AI ou fixados no tópico por uma pessoa. 

   ![Tópico na Pesquisa](../media/knowledge-management/search-topic-answer.png) 

A página de tópico pode ser exibida nos resultados da pesquisa, mesmo que o cartão de resposta do tópico não apareça.


## <a name="acronyms"></a>Acrônimos

Em Tópicos do Viva, você pode editar manualmente um tópico para incluir um acrônimo para ele como <b>um Nome Alternativo</b>. Isso permite que um usuário que está pesquisando apenas o acrônimo do tópico encontre a resposta do tópico por meio da Pesquisa da Microsoft.

[As Respostas de](/microsoftsearch/manage-acronyms) Acrônimo são um recurso fornecido pela Pesquisa da Microsoft e são gerenciados separadamente dos Tópicos do Viva.

## <a name="bookmarks-and-topics"></a>Indicadores e tópicos

[Indicadores](/microsoftsearch/manage-bookmarks) são um recurso de Pesquisa da Microsoft que ajudam as pessoas a encontrar rapidamente sites e ferramentas importantes com apenas uma pesquisa (por exemplo, uma ferramenta de reserva de viagens em um site externo fora do locatário do Microsoft 365). Eles são criados por administradores de pesquisa no Centro de administração do Microsoft 365. 

Para usuários que estão procurando informações sobre como reservar uma viagem para trabalhar:

- Se alguns usuários conhecem o nome da ferramenta de viagem (por exemplo, "Concur"), é mais fácil criar um indicador para ir diretamente para o site externo.
- Para usuários que pesquisam geralmente por "viagem", crie um tópico sobre "Viagem" que tenha as informações que eles esperam ver. Considere adicionar um link ao site externo Concur na descrição do tópico. Se o link for, em vez disso, para um site de reserva de viagem interno hospedado no locatário do Microsoft 365, você poderá adicioná-lo aos "Recursos Fixados".
 
### <a name="search-results-priority"></a>Prioridade de resultados da pesquisa 
 
Na experiência de pesquisa de usuários, quando um usuário pesquisa um termo como "viagem", os resultados da pesquisa serão exibidos na seguinte prioridade na Pesquisa da Microsoft
1. Tópicos publicados ou confirmados 
2. Indicadores
3. Tópicos sugeridos