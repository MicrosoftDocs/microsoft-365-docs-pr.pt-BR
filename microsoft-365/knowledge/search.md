---
title: Usar a Pesquisa da Microsoft para encontrar tópicos nos tópicos do Microsoft Viva
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Saiba como você pode pesquisar tópicos no Microsoft Viva.
ms.openlocfilehash: 484d2477f7e4dbef096a4b8a2d30095708c6cc3f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50108285"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Usar a Pesquisa da Microsoft para encontrar tópicos nos tópicos do Microsoft Viva

Embora os usuários de Tópicos do Viva possam encontrar tópicos por meio de destaques de tópicos em seus sites do SharePoint, eles também podem encontrá-los por meio da Pesquisa da Microsoft. 

## <a name="topic-answer"></a>Resposta de Tópico

Quando você procura um tópico específico na Pesquisa da Microsoft (por exemplo, "Saturno"), se um tópico existir e for encontrado, ele exibirá o resultado no formato de sugestão De respostas.

A resposta do tópico será exibida:
- Nome do tópico
- Nomes alternativos: Nomes alternativos ou acrônimos para o tópico.
- Definição: Descrição do tópico fornecido pela IA ou adicionado manualmente por uma pessoa.
- Pessoas sugeridas ou fixadas: pessoas sugeridas por IA ou fixadas no tópico por uma pessoa
- Recursos sugeridos ou fixados: arquivos, páginas ou sites sugeridos por IA ou fixados no tópico por uma pessoa. 

   ![Tópico na Pesquisa](../media/knowledge-management/search-topic-answer.png) 

A página de tópico pode ser exibida nos resultados da pesquisa mesmo se o cartão de resposta do tópico não aparecer.


## <a name="acronyms"></a>Acrônimos

Em Tópicos do Viva, você pode editar manualmente um tópico para incluir um acrônimo para ele como um <b>Nome Alternativo.</b> Isso permite que um usuário que está pesquisando apenas pelo acrônimo do tópico encontre a resposta do tópico por meio da Pesquisa da Microsoft.

[Respostas de](https://docs.microsoft.com/microsoftsearch/manage-acronyms) acrônimo é um recurso fornecido pela Pesquisa da Microsoft e é gerenciado separadamente dos Tópicos do Viva.

## <a name="bookmarks-and-topics"></a>Indicadores e tópicos

[Os indicadores](https://docs.microsoft.com/microsoftsearch/manage-bookmarks) são um recurso da Pesquisa da Microsoft que ajuda as pessoas a encontrar rapidamente sites e ferramentas importantes com apenas uma pesquisa (por exemplo, uma ferramenta de reserva de viagens em um site externo fora do locatário do Microsoft 365). Eles são criados por administradores de pesquisa no centro de administração do Microsoft 365. 

Para usuários que estão procurando informações sobre como reservar uma viagem de trabalho:

- Se alguns usuários sabem o nome da ferramenta de viagens (por exemplo, "Concur"), é mais fácil criar um indicador para ir diretamente para o site externo.
- Para usuários que pesquisam geralmente por "viagem", crie um tópico sobre "Viagem" que tenha as informações que esperam ver. Considere adicionar um link para o site externo Concur na descrição do tópico. Se o link for para um site de reserva de viagens interno hospedado no locatário do Microsoft 365, você poderá adicioná-lo aos "Recursos Fixados".
 
### <a name="search-results-priority"></a>Prioridade dos resultados da pesquisa 
 
Na experiência de pesquisa de usuários, quando um usuário procura um termo como "viagem", os resultados da pesquisa serão exibidos na seguinte prioridade na Pesquisa da Microsoft
1. Tópicos publicados ou confirmados 
2. Indicadores
3. Tópicos sugeridos 



