---
title: Compartilhar calendários com usuários externos
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 'Saiba como permitir que seus usuários compartilhem seus calendários com usuários externos para reuniões e compromissos. '
ms.openlocfilehash: 972e8376ae3d71b11205d4a6611dc6900c063ffe
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780056"
---
# <a name="share-calendars-with-external-users"></a>Compartilhar calendários com usuários externos

Muitas vezes, é necessário agendar reuniões com pessoas de fora de sua organização. Para simplificar o processo de encontrar horários de reuniões mutuamente aceitos, a Microsoft 365 permite que você disponibilize calendários para "usuários externos", aqueles que precisam ver o horário de disponibilidade, mas não têm contas de usuário para seu ambiente do Microsoft 365.
  
O compartilhamento de calendário é uma configuração global, o que significa que você, o administrador, pode habilitá-lo para todos os usuários no locatário. Depois que o compartilhamento é habilitado, os usuários podem usar o Outlook Web App para compartilhar seus calendários com qualquer pessoa dentro ou fora da organização. As pessoas dentro da organização podem exibir o calendário compartilhado lado a lado com seus próprios calendários. As pessoas de fora da organização receberão uma URL que poderá ser usada para exibir o calendário. Os usuários decidem quando e quanto compartilhar e quando manter seus calendários particulares.
  
> [!NOTE]
> If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information. 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a>Habilitar o compartilhamento de calendários usando o centro de administração do Microsoft 365

1. No centro de administração, vá para configurações da organização de **configurações** \> **Org Settings**. 
    
2. Na guia **Serviços** , selecione **calendário**.
  
3. Na página **calendário** que é aberta, escolha se você deseja permitir que seus usuários compartilhem seus calendários com pessoas de fora de sua organização que tenham o Microsoft 365 ou o Exchange.
    
4. Escolha se você deseja permitir que usuários anônimos (usuários sem credenciais de logon) acessem calendários por meio de um convite por email.

5. Escolha quais tipos de informações de calendário disponibilizar para os usuários. Você pode permitir todas as informações ou limitá-la somente a horário, assunto e local.

    
## <a name="invite-people-to-access-calendars"></a>Convidar pessoas para acessarem os calendários

Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions. 
  
