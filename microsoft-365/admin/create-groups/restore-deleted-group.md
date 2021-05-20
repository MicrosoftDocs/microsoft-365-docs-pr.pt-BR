---
title: Restaurar um grupo Microsoft 365 excluído
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
description: Um grupo excluído é mantido por 30 dias e você ainda pode restaurar o grupo. Após 30 dias, o grupo e seu conteúdo serão excluídos permanentemente.
ms.openlocfilehash: 285796ec45b1e6d77d46d7a0c39706f566bb8cf6
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582675"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Restaurar um grupo Microsoft 365 excluído

Se você tiver excluído um grupo, ele será mantido por 30 dias por padrão. Esse período de 30 dias é considerado uma "exclusão suave" porque você ainda pode restaurar o grupo. Após 30 dias, o grupo e seu conteúdo associado são excluídos permanentemente e não podem ser restaurados.

Quando um grupo de é restaurado, o seguinte conteúdo é restaurado:
  
- Azure Active Directory (AD) Microsoft 365 objeto Groups, propriedades e membros.
    
- Endereços de email do grupo.
    
- Exchange Online caixa de entrada compartilhada e calendário.
    
- SharePoint Site e arquivos de equipe online.
    
- Bloco de anotações do OneNote
    
- Planner
    
- Teams

- Yammer conteúdo de grupo e grupo (se o grupo Microsoft 365 foi criado Yammer)

> [!NOTE]
> Este artigo descreve a restauração apenas Microsoft 365 grupos. Todos os outros grupos não podem ser restaurados uma vez excluídos.

## <a name="restore-a-group"></a>Restaurar um grupo

# <a name="outlook"></a>[Outlook](#tab/outlook)

Se você for o proprietário de um grupo de Microsoft 365, poderá restaurar o grupo sozinho Outlook na Web seguindo estas etapas:

1. Na página [grupos excluídos,](https://outlook.office.com/people/group/deleted)selecione a opção **Gerenciar grupos** no nó **Grupos** e escolha **Excluído**.

2. Clique na guia **Restaurar** ao lado do grupo que você deseja restaurar.

Se o grupo excluído não aparecer aqui, contate um administrador.

# <a name="admin-center"></a>[Centro de administração](#tab/admin-center)

Se você for um administrador global ou um administrador de grupos, poderá restaurar um grupo excluído no Microsoft 365 de administração:

1. Acesse o [centro de administração](https://admin.microsoft.com).
2. Expanda **Grupos** e clique em **Grupos Excluídos.**
3. Selecione o grupo que você deseja restaurar e clique em **Restaurar grupo**.

> [!NOTE]
> Em alguns casos, pode levar até 24 horas para que o grupo e todos os seus dados sejam restaurados. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Tem perguntas sobre Microsoft 365 Grupos?

Visite o [microsoft tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para postar perguntas e participar de conversas sobre Microsoft 365 grupos. 
  
## <a name="related-content"></a>Conteúdo relacionado

[Gerenciar Microsoft 365 grupos com o PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artigo)
  
[Excluir grupos usando o cmdlet Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) (artigo)
  
[Gerenciar as configurações do site de equipe](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) conectado ao grupo (artigo)
  
[Excluir um grupo no Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (artigo)