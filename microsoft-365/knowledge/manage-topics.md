---
title: Gerenciar tópicos na central de tópicos no Microsoft Viva Topics
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
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 2443319d254130b38bb1047a633c85c160eadd8c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925995"
---
# <a name="manage-topics-in-the-topic-center"></a>Gerenciar tópicos na central de tópicos 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


No Centro de Tópicos do Viva, um gerente de conhecimento pode exibir a página Gerenciar tópicos para revisar **tópicos** que foram identificados em locais de origem do SharePoint, conforme especificado pelo administrador de conhecimento.  

   ![Central de Tópicos](../media/knowledge-management/topic-center.png) </br> 



Os gerentes de conhecimento ajudam a orientar tópicos descobertos por meio do ciclo de vida do tópico no qual os tópicos são:

- Sugerido: um tópico foi identificado pela AI e tem recursos de suporte suficientes, conexões e propriedades.
- Confirmado: um tópico sugerido pela AI é validado. A validação é feita por confirmação de um gerente de conhecimento. Além disso, um tópico pode ser confirmado se pelo menos dois usuários daem comentários positivos por meio da pergunta de comentários sobre o cartão de tópico.
- Publicado: um tópico confirmado que foi abordado: foram feitas edições manuais para melhorar sua qualidade.
- Removido: um tópico é rejeitado por um gerente de conhecimento e não será mais visível para os visualizadores. O tópico pode estar em qualquer estado quando é removido (sugerido, confirmado ou publicado). Quando um tópico publicado é removido, a página com os detalhes de cura precisará ser excluída manualmente por meio da Biblioteca de Páginas do centro de tópicos.

   ![Gráfico de ciclo de vida do tópico](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> Na página Gerenciar Tópicos, cada gerente de conhecimento só poderá ver tópicos em que eles tenham acesso aos arquivos e páginas do tópico. Isso será refletido nos tópicos listados nas guias Sugerido, Confirmado, Removido e Publicado. O tópico conta, no entanto, mostrar o total de contagens na organização.

## <a name="requirements"></a>Requisitos

Para gerenciar tópicos na central de tópicos, você precisa:
- Tenha uma licença de Tópicos do Viva.

- Tenha a [**permissão Quem pode gerenciar tópicos.**](./topic-experiences-user-permissions.md) Os administradores de conhecimento podem dar aos usuários essa permissão nas configurações de permissões do tópico Tópicos do Viva. 

Você não poderá exibir a página Gerenciar Tópicos na Central de Tópicos, a menos que tenha a permissão **Quem pode gerenciar tópicos.**

No centro de tópicos, um gerente de conhecimento pode revisar tópicos que foram identificados nos locais de origem do SharePoint especificados e podem confirmá-los ou rejeitá-los. Um gerente de conhecimento também pode criar e publicar novas páginas de tópicos se uma não foi encontrada na descoberta de tópicos ou editar as existentes, caso precisem ser atualizadas.


## <a name="review-suggested-topics"></a>Revisar tópicos sugeridos

Na página Central de Tópicos Gerenciar Tópicos, os tópicos que foram descobertos em seus locais de origem especificados do SharePoint serão listados na **guia Sugerido.** Se necessário, um gerente de conhecimento pode revisar tópicos não confirmados e optar por confirmá-los ou rejeitá-los.

   ![Tópicos sugeridos](../media/knowledge-management/quality-score.png) </br> 

Para revisar um tópico sugerido:

1. Na página **Gerenciar tópicos,** selecione a **guia Sugerido,** selecione o tópico para abrir a página de tópicos.</br>

2. Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página. A publicação de todas as edições moverá este tópico para a **guia Publicado.**

3. Depois de revisar o tópico, volte para a página Gerenciar tópicos. Para o tópico selecionado, você pode:

   - Selecione a marca de seleção para confirmar o tópico.
    
   - Selecione **o x** se quiser rejeitar o tópico.

    Os tópicos confirmados serão removidos da **lista Sugerida** e agora serão exibidos na **lista Confirmado.**

    Os tópicos rejeitados serão removidos da lista **Sugerida** e agora serão exibidos na **guia Removido.**

   </br> 

### <a name="quality-score"></a>Pontuação de qualidade

Cada tópico que aparece na página Tópicos Sugeridos tem uma pontuação <b>de</b> Qualidade atribuída a ele. A pontuação de Qualidade é um reflexo da quantidade de informações que o usuário médio verá para obter as informações sobre o tópico, tendo em mente que cada usuário pode ver mais ou menos informações devido às permissões que podem ou não ter sobre as informações em um tópico. 

A pontuação de qualidade pode ajudar a dar informações sobre os tópicos com mais informações e pode ser útil para encontrar tópicos que talvez precisem ser editados manualmente.  Por exemplo, um tópico com uma pontuação de qualidade menor pode ser o resultado de alguns usuários não terem permissões do SharePoint para arquivos ou sites pertinentes que a AI incluiu no tópico. Em seguida, um colaborador pode editar o tópico para incluir as informações (quando apropriado), que serão visualizadas para todos os usuários que podem exibir o tópico.

A pontuação de qualidade pode variar de 1 a 100. Um tópico recém-descoberto terá uma pontuação de qualidade de 0 até que dois ou mais usuários o tenham exibido. Cada pontuação de qualidade dos usuários é determinada por vários fatores, como a quantidade de conteúdo exibida para o usuário específico, que é controlada pelas permissões do usuário, pois cada página de tópico tem aparação de segurança no local para conteúdo gerado por IA. A pontuação de qualidade mostrada na guia Tópicos Sugeridos é uma média de pontuação individual de cada usuário.

### <a name="impressions"></a>Impressões

A <b>coluna Impressões</b> exibe o número de vezes que um tópico foi mostrado aos usuários finais. Isso inclui exibições por meio de cartões de tópicos na pesquisa, por meio de destaques de tópicos e por meio de exibições da central de tópicos. Ele não reflete o clique sobre esses tópicos, mas que o tópico foi exibido. A coluna Impressões mostrará tópicos nas guias Sugeridos, Confirmados, Publicados e Removidos na página Gerenciar Tópicos.


## <a name="confirmed-topics"></a>Tópicos confirmados

Na página Gerenciar tópicos, os tópicos que foram descobertos nos locais de origem especificados do SharePoint e foram confirmados por um gerente  de conhecimento ou "crowd-sourced" confirmados por duas ou mais pessoas por meio do mecanismo de comentários do cartão serão listados na guia Confirmado. Se necessário, um usuário com permissões para gerenciar tópicos pode revisar tópicos confirmados e optar por rejeitá-los.

Para revisar um tópico confirmado:

1. Na guia **Confirmado,** selecione o tópico para abrir a página de tópicos.</br>

2. Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.

Observe que você ainda pode optar por rejeitar um tópico confirmado.  Para fazer isso, vá para o tópico selecionado na lista Confirmado e selecione **o x se** quiser rejeitar o tópico.

## <a name="published-topics"></a>Tópicos publicados
Os tópicos publicados foram editados para que informações específicas sempre apareçam para quem encontrar a página. Os tópicos criados manualmente também estão listados aqui.

   ![Gerenciar tópicos](../media/knowledge-management/manage-topics-new.png) </br>