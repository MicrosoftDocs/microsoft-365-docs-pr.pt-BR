---
title: Restaurar um grupo excluído
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Saiba como restaurar um grupo do Microsoft 365 excluído.
ms.openlocfilehash: 8fb2cb3afdf390efae7854a040bb56df731cceaf
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307182"
---
# <a name="restore-a-deleted-group"></a>Restaurar um grupo excluído

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Se você tiver excluído um grupo, ele será mantido por 30 dias por padrão. Este período de 30 dias é considerado uma "exclusão reversível" porque você ainda pode restaurar o grupo. Após 30 dias, o grupo e seu conteúdo associado são excluídos permanentemente e não podem ser restaurados.

Quando um grupo de é restaurado, o seguinte conteúdo é restaurado:
  
- Azure Active Directory (AD) Microsoft 365 groups Object, Properties e Members.
    
- Endereços de email do grupo.
    
- Calendário e caixa de entrada compartilhada do Exchange Online.
    
- Arquivos e site de equipe do SharePoint Online.
    
- Bloco de anotações do OneNote
    
- Planner
    
- Teams

- Grupo e conteúdo de grupo do Yammer (se o grupo Microsoft 365 foi criado a partir do Yammer)

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a>Restaurar um grupo que você possui usando o Outlook na Web

Se você é o proprietário de um grupo do Microsoft 365, é possível restaurar o grupo sozinho no Outlook na Web seguindo estas etapas:

1. Na [página grupos excluídos](https://outlook.office.com/people/group/deleted), selecione a opção **gerenciar grupos** no nó **grupos** e, em seguida, escolha **excluído**.

2. Clique na guia **restaurar** ao lado do grupo que você deseja restaurar.

Se o grupo excluído não aparecer aqui, entre em contato com um administrador.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Restaurar um grupo no centro de administração do Microsoft 365

Se você for um administrador global ou um administrador de grupos, poderá restaurar um grupo excluído no centro de administração do Microsoft 365:

1. Acesse o [centro de administração](https://admin.microsoft.com).
2. Expanda **grupos**e, em seguida, clique em **grupos excluídos**.
3. Selecione o grupo que você deseja restaurar e clique em **restaurar grupo**.

> [!NOTE]
> Em alguns casos, pode levar até 24 horas para o grupo e todos os seus dados a serem restaurados. 
  
## <a name="permanently-delete-a-microsoft-365-group"></a>Excluir permanentemente um grupo do Microsoft 365

Às vezes, você pode querer limpar permanentemente um grupo sem esperar que o período de exclusão reversível de 30 dias expire. Para fazer isso, inicie o PowerShell e execute este comando para obter a ID de objeto do grupo:
  
```
Get-AzureADMSDeletedGroup
```

Anote a ID de objeto do grupo, ou grupos, que você deseja excluir permanentemente.
  
> [!CAUTION]
> Ao limpar o grupo, você removerá o grupo e os dados nele para sempre. 
  
Para limpar o grupo, execute o seguinte comando no PowerShell:
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

Para confirmar que o grupo foi limpo, execute o cmdlet  *Get-AzureADMSDeletedGroup*  novamente para confirmar que ele não aparece mais na lista de grupos temporariamente excluídos. Em alguns casos pode levar até 24 horas para que o grupo e todos os dados nele sejam excluídos permanentemente. 
  
## <a name="got-questions-about-microsoft-365-groups"></a>Você tem dúvidas sobre os grupos da Microsoft 365?

Visite a [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para postar perguntas e participar de conversas sobre os grupos do Microsoft 365. 
  
## <a name="related-articles"></a>Artigos relacionados

[Gerenciar os grupos do Microsoft 365 com o PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[Excluir grupos usando o cmdlet Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Gerenciar as configurações do site de equipe conectado ao grupo](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Excluir um grupo no Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
