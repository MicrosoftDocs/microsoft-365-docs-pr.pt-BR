---
title: Gerenciar tópicos no centro de tópicos no Microsoft Viva Topics
description: Como gerenciar tópicos no centro de tópicos.
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
ms.openlocfilehash: f2429b0ffdd4a238bc9322ae9199eebbbfd407b5
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651147"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a>Gerenciar tópicos no centro de tópicos no Microsoft Viva Topics

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

No centro de tópicos Tópicos do Viva, um gerente de conhecimento pode exibir a página Gerenciar tópicos para revisar **tópicos** identificados nos locais de origem conforme especificado pelo administrador de conhecimento.  

   ![Central de Tópicos](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a>Estágios do tópico

Os gerentes de conhecimento ajudam a orientar tópicos descobertos por meio dos vários estágios de ciclo de vida de tópicos: **Sugerido** **,** Confirmado, **Publicado** e **Removido.**

   ![Gráfico de ciclo de vida do tópico](../media/knowledge-management/topic-lifecycle.png) 

- **Sugerido**: um tópico foi identificado pela IA e tem recursos, conexões e propriedades de suporte suficientes. (Eles são marcados como **um Tópico Sugerido** na interface do usuário.)

- **Confirmado**: um tópico que foi descoberto pela AI e foi validado. A validação de tópico ocorre quando:

   - Um gerente de conhecimento confirma um tópico. Um gerente de [conhecimento confirma um tópico na](manage-topics.md#confirmed-topics) página Gerenciar **tópicos.**

   - Vários usuários confirmam um tópico. Deve haver uma rede de dois votos positivos recebidos dos usuários que votaram usando o mecanismo de comentários no cartão de tópico. Por exemplo, se um usuário votou positivo e um usuário votou negativo para um tópico específico, você ainda precisaria de mais dois votos positivos para que o tópico fosse confirmado.
 
- **Publicado**: um tópico que foi abordado. As edições manuais foram feitas para melhorar sua qualidade ou foram criadas por um usuário.

- **Removido**: um tópico que foi rejeitado e não estará mais visível para os visualizadores. Um tópico pode ser removido em qualquer estado (sugerido, confirmado ou publicado). A remoção de tópico ocorre quando:

   - Um gerente de conhecimento remove um tópico. Um gerente de conhecimento remove um tópico na página **Gerenciar** tópicos.

   - Vários usuários lançam votos negativos usando o mecanismo de comentários no cartão de tópico. Para que um tópico seja removido, deve haver uma rede de dois votos negativos recebidos dos usuários. Por exemplo, se um usuário votou negativo e um usuário votou positivo para um tópico específico, você ainda precisaria de mais dois votos negativos para que o tópico fosse removido.

  Quando um tópico publicado é removido, a página com os detalhes de cura precisará ser excluída manualmente por meio da Biblioteca de Páginas do centro de tópicos.

> [!Note] 
> Na página **Gerenciar tópicos,** cada gerente de conhecimento só poderá ver tópicos em que eles tenham acesso aos arquivos e páginas subjacentes conectados ao tópico. Essa aparação de permissão será refletida na lista de tópicos que aparecem nas guias **Sugeridas** **,** **Confirmadas,** Publicadas e **Removidas.** O tópico conta, no entanto, mostrar o total de contagens na organização, independentemente das permissões.

## <a name="requirements"></a>Requisitos

Para gerenciar tópicos no centro de tópicos, você precisa:
- Ter uma licença do Viva Topics.

- Ter a [**Who pode gerenciar a permissão de**](./topic-experiences-user-permissions.md) tópicos. Os Administradores de conhecimento podem dar aos usuários essa permissão nas configurações de permissões do tópico do Viva Topics. 

Você não poderá exibir a página Gerenciar tópicos no centro de **tópicos,** a menos que você tenha a permissão Who **possa gerenciar tópicos.**

No centro de tópicos, um gerente de conhecimento pode revisar tópicos que foram identificados nos locais de origem especificados e podem confirmá-los ou removê-los. Um gerente de conhecimento também pode criar e publicar novas páginas de tópicos se uma não foi encontrada na descoberta de tópicos ou editar as existentes, caso precisem ser atualizadas.

## <a name="review-suggested-topics"></a>Revisar tópicos sugeridos

Na página **Gerenciar tópicos,** os tópicos que foram descobertos em seus locais SharePoint de origem especificados serão listados na **guia Sugerido.** Se necessário, um gerente de conhecimento pode revisar tópicos não confirmados e optar por confirmá-los ou removê-los.

   ![Tópicos sugeridos](../media/knowledge-management/quality-score.png) 

Para revisar um tópico sugerido:

1. Na página **Gerenciar tópicos,** selecione a guia **Sugerido** e selecione o tópico para abrir a página de tópicos.

2. Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página. A publicação de todas as edições moverá este tópico para a **guia Publicado.**

3. Depois de revisar o tópico, volte para a **página Gerenciar tópicos.** Para o tópico selecionado, você pode:

   - Selecionar a marca de seleção para confirmar o tópico.
    
   - Selecione **o x** se quiser remover o tópico.

    Os tópicos confirmados serão removidos da **lista Sugerida** e agora serão exibidos na **lista Confirmado.**

    Os tópicos removidos serão removidos da lista **Sugerida** e agora serão exibidos na **guia Removido.**

### <a name="quality-score"></a>Pontuação de qualidade

Cada tópico que aparece na página **Tópicos** Sugeridos tem uma pontuação de qualidade atribuída a ele. A pontuação de qualidade é um reflexo da quantidade de informações que o usuário médio verá para obter as informações sobre o tópico, tendo em mente que cada usuário pode ver mais ou menos informações devido às permissões que podem ou não ter sobre as informações em um tópico. 

A pontuação de qualidade pode ajudar a dar informações sobre os tópicos com mais informações e pode ser útil para encontrar tópicos que podem precisar ser editados manualmente. Por exemplo, um tópico com uma pontuação de qualidade menor pode ser o resultado de alguns usuários não terem SharePoint permissões para arquivos ou sites pertinentes que a AI incluiu no tópico. Um colaborador poderá, em seguida, editar o tópico para incluir as informações (quando apropriado), que poderão ser visualizadas para todos os usuários que podem exibir o tópico.

### <a name="impressions"></a>Impressões

A **coluna Impressões** exibe o número de vezes que um tópico foi mostrado aos usuários finais. Isso inclui exibições por meio de cartões de resposta de tópicos na pesquisa e nos destaques do tópico. Ele não reflete o clique sobre esses tópicos, mas que o tópico foi exibido. A **coluna Impressões** mostrará tópicos nas guias **Sugeridas** **,** Confirmadas, Publicadas e Removidas na página **Gerenciar** tópicos. 

## <a name="confirmed-topics"></a>Tópicos confirmados

Na página Gerenciar **tópicos,** os tópicos que foram descobertos em seus locais de origem do SharePoint especificados e foram confirmados por um gerente de conhecimento ou "crowdsourced"  confirmados por uma rede de duas ou mais pessoas (balanceando votos de usuários negativos contra votos positivos de usuários) por meio do mecanismo de feedback de cartão serão listados na guia Confirmado. Se necessário, um usuário com permissões para gerenciar tópicos pode revisar tópicos confirmados e optar por rejeitá-los.

Para revisar um tópico confirmado:

1. Na guia **Confirmados**, selecione o tópico para abrir a página de tópicos.

2. Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.

Observe que você ainda pode optar por rejeitar um tópico confirmado. Para fazer isso, vá para  o tópico selecionado na guia Confirmado e selecione **o x** se quiser rejeitar o tópico.

## <a name="published-topics"></a>Tópicos publicados

Os tópicos publicados foram editados para que informações específicas sempre apareçam para quem encontrar a página. Os tópicos criados manualmente também são listados aqui.

   ![Gerenciar tópicos](../media/knowledge-management/manage-topics-new.png)

## <a name="topic-count-dashboard"></a>Painel de contagem de tópicos

Este gráfico no painel de exibição permite que você veja o número de tópicos no centro de tópicos do Viva Tópicos. O gráfico mostra as contagens de tópicos por estágio de ciclo de vida de tópicos e também mostra como as contagens de tópicos têm tendência ao longo do tempo. Os gerentes de conhecimento podem monitorar visualmente a taxa na qual novos tópicos estão sendo descobertos pela AI e a taxa na qual os tópicos estão sendo confirmados ou publicados pelo gerente de conhecimento ou pelas ações do usuário.

Os gerentes de conhecimento podem ver uma contagem diferente de tópicos representados na lista de tópicos na página Gerenciar **tópicos** do que eles veem no painel. Isso porque um gerente de conhecimento pode não ter acesso a todos os tópicos. A contagem apresentada no exibição do painel é feita antes da aplicação de corte de permissão. 

   ![Captura de tela do painel de contagem de tópicos](../media/knowledge-management/topic-count-dashboard.png)
