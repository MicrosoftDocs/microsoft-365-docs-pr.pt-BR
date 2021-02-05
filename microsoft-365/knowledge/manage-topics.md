---
title: Gerenciar tópicos no Centro de Tópicos nos Tópicos do Microsoft Viva
description: Como gerenciar tópicos na Central de Tópicos.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 45e8f26823998278f9a332d2ea1e362b77f2032b
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107177"
---
# <a name="manage-topics-in-the-topic-center"></a>Gerenciar tópicos no Centro de Tópicos 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


No Centro de Tópicos do Viva, um gerente de conhecimento pode exibir a página Gerenciar tópicos para revisar os **tópicos** identificados nos locais de origem do SharePoint, conforme especificado pelo administrador de conhecimento.  

   ![Central de Tópicos](../media/knowledge-management/topic-center.png) </br> 



Os gerentes de conhecimento ajudam a orientar tópicos descobertos no ciclo de vida do tópico no qual os tópicos são:

- Sugerido: um tópico foi identificado pela ia e tem recursos, conexões e propriedades de suporte suficientes.
- Confirmado: Um tópico sugerido pela IA é validado. A validação é feita por confirmação de um gerente de conhecimento. Além disso, um tópico pode ser confirmado se pelo menos dois usuários daem feedback positivo por meio da pergunta de comentários no cartão de tópico.
- Publicado: um tópico confirmado que foi abordado: foram feitas edições manuais para melhorar sua qualidade.
- Removido: um tópico é rejeitado por um gerente de conhecimento e não estará mais visível para os visitantes. O tópico pode estar em qualquer estado quando é removido (sugerido, confirmado ou publicado). Quando um tópico publicado for removido, a página com os detalhes da seleção precisará ser excluída manualmente por meio da Biblioteca de Páginas do centro de tópicos.

   ![Gráfico do Ciclo de Vida do Tópico](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> Na página Gerenciar Tópicos, cada gerente de conhecimento só poderá ver os tópicos em que tiver acesso aos arquivos e páginas do tópico. Isso será refletido nos tópicos listados nas guias Sugerido, Confirmado, Removido e Publicado. O tópico conta, no entanto, mostra o total de contagens na organização.

## <a name="requirements"></a>Requisitos

Para gerenciar tópicos na Central de Tópicos, você precisa:
- Ter uma licença de Tópicos do Viva.

- Ter a [**permissão Quem pode gerenciar tópicos.**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) Os administradores de conhecimento podem dar aos usuários essa permissão nas configurações de permissões do tópico Tópicos do Viva. 

Você não poderá exibir a página Gerenciar Tópicos na Central de Tópicos, a menos que tenha a **permissão Quem pode gerenciar tópicos.**

No centro de tópicos, um gerente de conhecimento pode revisar tópicos que foram identificados nos locais de origem do SharePoint especificados e pode confirmá-los ou rejeitá-los. Um gerente de conhecimento também pode criar e publicar novas páginas de tópico se uma não foi encontrada na descoberta de tópicos ou editar as existentes se elas precisam ser atualizadas.


## <a name="review-suggested-topics"></a>Revisar tópicos sugeridos

Na página Gerenciar Tópicos da Central de Tópicos, os tópicos descobertos nos locais de origem especificados do SharePoint serão listados na **guia Sugeridos.** Se necessário, um gerente de conhecimento pode revisar tópicos não confirmados e optar por confirmá-los ou rejeitá-los.

   ![Tópicos Sugeridos](../media/knowledge-management/quality-score.png) </br> 

Para revisar um tópico sugerido:

1. Na página **Gerenciar tópicos,** selecione a **guia Sugerido,** selecione o tópico para abrir a página de tópicos.</br>

2. Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página. A publicação de todas as edições move este tópico para a **guia** Publicado.

3. Depois de analisar o tópico, volte para a página Gerenciar tópicos. Para o tópico selecionado, você pode:

   - Selecione a marca de seleção para confirmar o tópico.
    
   - Selecione o **x** se quiser rejeitar o tópico.

    Os tópicos confirmados serão removidos **da lista Sugeridos** e agora serão exibidos na **lista Confirmado.**

    Os tópicos rejeitados serão removidos **da lista Sugeridos** e agora serão exibidos na **guia** Removido.

   </br> 

### <a name="quality-score"></a>Pontuação de qualidade

Cada tópico que aparece na página Tópicos Sugeridos tem uma <b>pontuação</b> de Qualidade atribuída a ela. A Pontuação de Qualidade é um reflexo da quantidade de informações que o usuário médio verá para obter as informações sobre o tópico, tendo em mente que cada usuário pode ver mais ou menos informações devido às permissões que eles podem ou não ter sobre as informações em um tópico. 

A Pontuação de Qualidade pode ajudar a dar informações sobre os tópicos com mais informações e pode ser útil para encontrar tópicos que talvez precisem ser editados manualmente.  Por exemplo, um tópico com uma pontuação de qualidade inferior pode ser o resultado de alguns usuários não terem permissões do SharePoint para arquivos ou sites pertinentes que a IA incluiu no tópico. Em seguida, um colaborador pode editar o tópico para incluir as informações (quando apropriado), o que poderá ser visualizado para todos os usuários que podem exibir o tópico.

A pontuação de Qualidade pode variar de 1 a 100. Um tópico recém-descoberto terá uma pontuação de qualidade de 0 até que dois ou mais usuários o tenham visualizado. A pontuação de qualidade de cada usuário é determinada por uma série de fatores, como a quantidade de conteúdo exibido para o usuário específico, que é controlada pelas permissões do usuário, pois cada página de tópico tem a aparação de segurança no lugar para conteúdo gerado por IA. A pontuação de Qualidade mostrada na guia Tópicos sugeridos é uma média de pontuação individual de cada usuário.

### <a name="impressions"></a>Impressões

A <b>coluna Impressões</b> exibe o número de vezes que um tópico foi mostrado para os usuários finais. Isso inclui exibições por meio de cartões de tópico na pesquisa, por meio de destaques de tópicos e por meio de exibições central de tópicos. Ele não reflete o clique sobre esses tópicos, mas que o tópico foi exibido. A coluna Impressões será aberta para tópicos nas guias Sugerido, Confirmado, Publicado e Removido na página Gerenciar Tópicos.


## <a name="confirmed-topics"></a>Tópicos confirmados

Na página Gerenciar tópicos, os tópicos que foram descobertos em seus locais de origem especificados do SharePoint e foram confirmados por um  gerente de conhecimento ou "de origem de lotes" confirmados por duas ou mais pessoas por meio do mecanismo de comentários do cartão serão listados na guia Confirmado. Se necessário, um usuário com permissões para gerenciar tópicos pode revisar tópicos confirmados e optar por rejeitá-los.

Para revisar um tópico confirmado:

1. Na guia **Confirmado,** selecione o tópico para abrir a página de tópico.</br>

2. Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.

Observe que você ainda pode optar por rejeitar um tópico confirmado.  Para fazer isso, vá para o tópico selecionado na lista Confirmado e selecione **o x** se quiser rejeitar o tópico.

## <a name="published-topics"></a>Tópicos publicados
Tópicos publicados foram editados para que informações específicas sempre apareçam para quem encontrar a página. Os tópicos criados manualmente também estão listados aqui.

   ![Gerenciar tópicos](../media/knowledge-management/manage-topics-new.png) </br> 




