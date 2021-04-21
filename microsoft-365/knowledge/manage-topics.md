---
title: Gerenciar tópicos no centro de tópicos no Microsoft Viva Topics
description: Como gerenciar tópicos na Central de Tópicos.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 4532f5685fdde7c89ca59e5c22e1ad8afdf2b112
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904029"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a>Gerenciar tópicos no centro de tópicos no Microsoft Viva Topics

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


No centro de tópicos Tópicos do Viva, um gerente de conhecimento pode exibir a página Gerenciar tópicos para revisar **tópicos** identificados nos locais de origem conforme especificado pelo administrador de conhecimento.  

   ![Central de Tópicos](../media/knowledge-management/topic-center.png) </br> 



Os gerentes de conhecimento ajudam a orientar tópicos descobertos por meio dos vários estágios de ciclo de vida de tópicos:

- **Sugerido**: um tópico foi identificado pela AI e tem recursos de suporte suficientes, conexões e propriedades.
- **Confirmado**: Um tópico sugerido pela AI é validado. A validação é feita por confirmação de um gerente de conhecimento. Além disso, um tópico pode ser confirmado se houver 2 votos positivos líquidos dos usuários finais recebidos por meio dos mecanismos de feedback no cartão de tópico.
- **Publicado**: Um tópico confirmado que foi abordado: foram feitas edições manuais para melhorar sua qualidade.
- **Removido**: um tópico é rejeitado por um gerente de conhecimento e não será mais visível para os visualizadores. O tópico pode estar em qualquer estado quando é removido (sugerido, confirmado ou publicado). Quando um tópico publicado é removido, a página com os detalhes de cura precisará ser excluída manualmente por meio da Biblioteca de Páginas do centro de tópicos.

   ![Gráfico de ciclo de vida do tópico](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> Na página Gerenciar Tópicos, cada gerente de conhecimento só poderá ver tópicos em que eles tenham acesso aos arquivos e páginas subjacentes conectados ao tópico. Essa aparação de permissão será refletida na lista de tópicos que aparecem nas guias **Sugeridas** **,** **Confirmadas,** Removidas e **Publicadas.** O tópico conta, no entanto, mostrar o total de contagens na organização, independentemente das permissões.

## <a name="requirements"></a>Requisitos

Para gerenciar tópicos no centro de tópicos, você precisa:
- Tenha uma licença de Tópicos do Viva.

- Tenha a [**permissão Quem pode gerenciar tópicos.**](./topic-experiences-user-permissions.md) Os administradores de conhecimento podem dar aos usuários essa permissão nas configurações de permissões do tópico Tópicos do Viva. 

Você não poderá exibir a página Gerenciar Tópicos no centro de tópicos, a menos que você tenha a permissão **Quem pode gerenciar tópicos.**

No centro de tópicos, um gerente de conhecimento pode revisar tópicos que foram identificados nos locais de origem especificados e podem confirmá-los ou rejeitá-los. Um gerente de conhecimento também pode criar e publicar novas páginas de tópicos se uma não foi encontrada na descoberta de tópicos ou editar as existentes, caso precisem ser atualizadas.


## <a name="review-suggested-topics"></a>Revisar tópicos sugeridos

Na página Gerenciar Tópicos do centro de tópicos, os tópicos que foram descobertos em seus locais de origem especificados do SharePoint serão listados na **guia Sugerido.** Se necessário, um gerente de conhecimento pode revisar tópicos não confirmados e optar por confirmá-los ou rejeitá-los.

   ![Tópicos sugeridos](../media/knowledge-management/quality-score.png) </br> 

Para revisar um tópico sugerido:

1. Na página **Gerenciar tópicos,** selecione a **guia Sugerido,** selecione o tópico para abrir a página de tópicos.</br>

2. Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página. A publicação de todas as edições moverá este tópico para a **guia Publicado.**

3. Depois de revisar o tópico, volte para a página Gerenciar Tópicos. Para o tópico selecionado, você pode:

   - Selecione a marca de seleção para confirmar o tópico.
    
   - Selecione **o x** se quiser rejeitar o tópico.

    Os tópicos confirmados serão removidos da **lista Sugerida** e agora serão exibidos na **lista Confirmado.**

    Os tópicos rejeitados serão removidos da lista **Sugerida** e agora serão exibidos na **guia Removido.**

   </br> 

### <a name="quality-score"></a>Pontuação de qualidade

Cada tópico que aparece na página Tópicos Sugeridos tem uma pontuação de qualidade atribuída a ele. A pontuação de qualidade é um reflexo da quantidade de informações que o usuário médio verá para obter as informações sobre o tópico, tendo em mente que cada usuário pode ver mais ou menos informações devido às permissões que podem ou não ter sobre as informações em um tópico. 

A pontuação de qualidade pode ajudar a dar informações sobre os tópicos com mais informações e pode ser útil para encontrar tópicos que podem precisar ser editados manualmente. Por exemplo, um tópico com uma pontuação de qualidade menor pode ser o resultado de alguns usuários não terem permissões do SharePoint para arquivos ou sites pertinentes que a AI incluiu no tópico. Em seguida, um colaborador pode editar o tópico para incluir as informações (quando apropriado), que serão visualizadas para todos os usuários que podem exibir o tópico.

### <a name="impressions"></a>Impressões

A **coluna Impressões** exibe o número de vezes que um tópico foi mostrado aos usuários finais. Isso inclui exibições por meio de cartões de resposta de tópicos na pesquisa e nos destaques do tópico. Ele não reflete o clique sobre esses tópicos, mas que o tópico foi exibido. A **coluna Impressões** mostrará tópicos nas guias **Sugeridas** **,** Confirmadas, Publicadas e Removidas na página Gerenciar Tópicos. 

## <a name="confirmed-topics"></a>Tópicos confirmados

Na página Gerenciar Tópicos, os tópicos que foram descobertos em seus locais de origem especificados do SharePoint e foram confirmados por um gerente de conhecimento ou "crowdsourced" confirmados por uma rede de duas ou mais pessoas (balanceamento de votos de usuários negativos contra votos positivos de usuários) por meio do mecanismo de feedback de cartão serão listados na guia Confirmado.  Se necessário, um usuário com permissões para gerenciar tópicos pode revisar tópicos confirmados e optar por rejeitá-los.

Para revisar um tópico confirmado:

1. Na guia **Confirmado,** selecione o tópico para abrir a página de tópicos.</br>

2. Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.

Observe que você ainda pode optar por rejeitar um tópico confirmado. Para fazer isso, vá para  o tópico selecionado na guia Confirmado e selecione **o x** se quiser rejeitar o tópico.

## <a name="published-topics"></a>Tópicos publicados
Os tópicos publicados foram editados para que informações específicas sempre apareçam para quem encontrar a página. Os tópicos criados manualmente também estão listados aqui.

   ![Gerenciar tópicos](../media/knowledge-management/manage-topics-new.png) </br>
