---
title: Restaurar um grupo excluído do Microsoft 365
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Saiba como restaurar um grupo excluído do Microsoft 365.
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910541"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Restaurar um grupo excluído do Microsoft 365

Se você tiver excluído um grupo, ele será mantido por 30 dias por padrão. Esse período de 30 dias é considerado uma "exclusão suave" porque você ainda pode restaurar o grupo. Após 30 dias, o grupo e seu conteúdo associado são excluídos permanentemente e não podem ser restaurados.

Quando um grupo de é restaurado, o seguinte conteúdo é restaurado:
  
- Objeto, propriedades e membros do Microsoft 365 Groups do Azure Active Directory (AD).
    
- Endereços de email do grupo.
    
- Caixa de entrada e calendário compartilhados do Exchange Online.
    
- Arquivos e sites de equipe do SharePoint Online.
    
- Bloco de anotações do OneNote
    
- Planner
    
- Teams

- Conteúdo de grupo e grupo do Yammer (Se o grupo do Microsoft 365 foi criado a partir do Yammer)

> [!NOTE]
> Este artigo descreve a restauração apenas de grupos do Microsoft 365. Todos os outros grupos não podem ser restaurados uma vez excluídos.

## <a name="restore-a-group"></a>Restaurar um grupo

# <a name="outlook"></a>[Outlook](#tab/outlook)

Se você for o proprietário de um grupo do Microsoft 365, poderá restaurar o grupo por conta própria no Outlook na Web seguindo estas etapas:

1. Na página [grupos excluídos,](https://outlook.office.com/people/group/deleted)selecione a opção **Gerenciar grupos** no nó **Grupos** e escolha **Excluído**.

2. Clique na guia **Restaurar** ao lado do grupo que você deseja restaurar.

Se o grupo excluído não aparecer aqui, contate um administrador.

# <a name="admin-center"></a>[Centro de administração](#tab/admin-center)

Se você for um administrador global ou um administrador de grupos, poderá restaurar um grupo excluído no centro de administração do Microsoft 365:

1. Acesse o [centro de administração](https://admin.microsoft.com).
2. Expanda **Grupos** e clique em **Grupos Excluídos.**
3. Selecione o grupo que você deseja restaurar e clique em **Restaurar grupo**.

> [!NOTE]
> Em alguns casos, pode levar até 24 horas para que o grupo e todos os seus dados sejam restaurados. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Tem dúvidas sobre grupos do Microsoft 365?

Visite a [Comunidade do Microsoft Tech para](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) postar perguntas e participar de conversas sobre grupos do Microsoft 365. 
  
## <a name="related-articles"></a>Artigos relacionados

[Gerenciar grupos do Microsoft 365 com o PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[Excluir grupos usando o cmdlet Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup)
  
[Gerenciar as configurações do site de equipe conectado ao grupo](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Excluir um grupo no Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)