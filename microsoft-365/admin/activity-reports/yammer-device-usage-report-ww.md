---
title: Relatórios do Microsoft 365 no centro de administração-relatório de uso de dispositivos do Yammer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenha o relatório de uso do dispositivo Yammer para saber quais dispositivos seus usuários estão usando o Yammer.
ms.openlocfilehash: fae76e9ef769248217140c059004efc7ad330928
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779289"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Relatórios do Microsoft 365 no centro de administração-relatório de uso de dispositivos do Yammer

O painel de **relatórios** do Microsoft 365 mostra a visão geral das atividades em todos os produtos de sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).
  
Os relatórios de uso de dispositivos do Yammer fornecem informações sobre em quais dispositivos seus usuários estão utilizando o Yammer. Você pode visualizar o número de usuários por dia por tipo de dispositivo e o número de usuários por tipo de dispositivo. Você pode visualizar ambos de acordo com um período específico de tempo. Você também pode visualizar detalhes por usuário.
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios.  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Como posso obter o relatório de uso de dispositivos do Yammer?

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
2. Na página inicial do painel, clique no botão **Exibir mais** no cartão do Yammer.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Interpretar o relatório de uso do dispositivo do Yammer

Você pode exibir o uso no relatório do OneDrive escolhendo a guia **uso do dispositivo** .<br/>![Microsoft 365 Reports-relatório de uso de dispositivo do Microsoft Yammer.](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

Selecione **escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Relatório de uso do dispositivo Yammer-escolher colunas](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

Você também pode exportar os dados do relatório para um arquivo. csv do Excel selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 
  
|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|Nome de usuário  <br/> |O endereço de email do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo. Esta grade mostra os usuários que fizeram logon no Yammer usando a conta do Microsoft 365 ou que fizeram logon na rede usando o single sign-on. <br/> |
|Nome de exibição  <br/> |O nome completo do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo.  <br/> |
|Estado do usuário  <br/> |Um dos três valores: Active, Deleted ou Suspended. Esses relatórios mostram os dados de usuários ativos, suspensos e excluídos. Eles não refletem os usuários pendentes, pois os usuários pendentes não podem publicar, ler ou curtir uma mensagem.   <br/> |
|Data de alteração de estado (UTC)  <br/> |A data em que o estado do usuário foi alterado no Yammer.  <br/> |
|Data da última atividade (UTC)  <br/> |A última data (UTC) que o usuário participou em uma atividade do Yammer.  <br/> |
|Web  <br/> |Indica se o usuário usou o Yammer na Web.  <br/> |
|Windows Phone  <br/> | Indica se o usuário usou o yammer em um Windows Phone.  <br/> |
|Celular Android  <br/> |Indica se o usuário usou o yammer em um telefone Android. <br/>|
|iPhone <br/> | Indica se o usuário usou o yammer em um iPhone.  <br/> |
|iPad  <br/> |Indica se o usuário usou o yammer em um iPad. <br/>|
|outro  <br/> |Indica se o usuário usou o yammer em outro dispositivo, não listado anteriormente. <br/>|
|||