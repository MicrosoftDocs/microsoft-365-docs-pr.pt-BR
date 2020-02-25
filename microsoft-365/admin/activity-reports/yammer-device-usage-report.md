---
title: Relatórios do Microsoft 365 no centro de administração-relatório de uso de dispositivos do Yammer
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b793ffdd-effa-43d0-849a-b1ca2e899f38
description: 'Obtenha o relatório de uso do dispositivo Yammer para saber quais dispositivos seus usuários estão usando o Yammer. '
ms.openlocfilehash: 5202fd2ebe3e99182ecf7cd2d9bee77be0573cde
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237172"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Relatórios do Microsoft 365 no centro de administração-relatório de uso de dispositivos do Yammer

O painel de **relatórios** do Microsoft 365 mostra a visão geral das atividades em todos os produtos de sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).
  
Os relatórios de uso de dispositivos do Yammer fornecem informações sobre em quais dispositivos seus usuários estão utilizando o Yammer. Você pode visualizar o número de usuários por dia por tipo de dispositivo e o número de usuários por tipo de dispositivo. Você pode visualizar ambos de acordo com um período específico de tempo. Você também pode visualizar detalhes por usuário.
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint ou Skype for Business para ver os relatórios. 
  
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Como posso obter o relatório de uso de dispositivos do Yammer?

1. No centro de administração do, vá para a página**Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. No menu suspenso **selecionar um relatório** , selecione **uso do dispositivo**do **Yammer** \> .
  
## <a name="interpret-the-yammer-activity-report"></a>Interpretar o relatório de atividades do Yammer

Você pode ver detalhes de uso do dispositivo Yammer dos seus usuários examinando os gráficos **Usuários** e **Distribuição**. 
  
O relatório de uso do dispositivo contém as informações a seguir.
  
- Use as guias de dia para exibir as tendências de relatório de atividade de **uso de dispositivos do Yammer** nos últimos sete dias, 30 dias, 90 dias ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela mostrará dados de até 28 dias a partir da data atual (não a data em que o relatório foi gerado). 
    
- Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas.
    
- Você pode visualizar o gráfico **Usuários** para ver o número de usuários por dia por tipo de dispositivo.<br/>![Exibição de usuários no gráfico de uso de dispositivos do Yammer](../media/ecfba1ec-fbea-4491-88da-1fb19b4d5629.png)<br/>![Relatório de uso do dispositivo Yammer mostrando o modo de exibição usuários](../media/f396865a-ad6e-4f8b-a145-cc3865b352f4.png)
  
- Você pode visualizar o gráfico **Distribuição** para ver o número de usuários por tipo de dispositivo.<br/>![Modo de exibição de distribuição no relatório de uso de dispositivos do Yammer](../media/7a0b152e-2d2b-4d23-8dc2-046be53b724f.png)<br/>![Relatório de uso de dispositivos do Yammer](../media/780c351d-7a1d-451d-8c16-4c454ef58aa8.png)
  
- A tabela **Detalhes** sob o gráfico mostra um detalhamento do uso do dispositivo Yammer no nível de cada usuário. 
    
    Você também pode adicionar e remover colunas. As colunas disponíveis são:
    
  - **Nome de usuário** é o endereço de email do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo. 
    
    Esta grade mostra os usuários que fizeram logon no Yammer usando a conta do Microsoft 365 ou que fizeram logon na rede usando o single sign-on.
    
  - **Nome para exibição** é o nome completo do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo. 
    
  - **Estado do usuário** é um dos três valores: ativos, excluídos ou suspensos. 
    
    Esses relatórios mostram os dados de usuários ativos, suspensos e excluídos. Eles não refletem os usuários pendentes, pois os usuários pendentes não podem publicar, ler ou curtir uma mensagem.
    
  - **Web** indica se o usuário usou o Yammer na Web. 
    
  - **Telefone Windows** indica se o usuário usou o Yammer em um telefone Windows 
    
  - **Telefone Android** indica se o usuário usou o Yammer em um telefone Android. 
    
  - **iPhone** indica se o usuário usou o Yammer em um iPhone. 
    
  - **iPad** indica se o usuário usou o Yammer em um iPad. 
    
  - **Outro** indica se o usuário usou o Yammer em outro dispositivo não listado anteriormente. 
    
    Se as políticas da organização impedem a exibição de relatórios em que as informações do usuário podem ser identificadas, você pode alterar as configurações de privacidade para todos esses relatórios. Confira a seção **como ocultar detalhes de nível de usuário?** nos [relatórios de atividades no centro de administração do Microsoft 365](activity-reports.md).
    
- Você também pode exportar os dados do relatório para um arquivo. csv do Excel, selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 
    

