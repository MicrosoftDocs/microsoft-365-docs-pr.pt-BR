---
title: Etapa 7 - Excluir a conta de usuário de um ex-funcionário
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Siga estas etapas para excluir a conta de usuário de um ex-funcionário.
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244153"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>Etapa 7 - Excluir a conta de usuário de um ex-funcionário

Depois de salvar e acessar todos os dados de usuário do ex-funcionário, você pode excluir a conta do ex-funcionário.

> [!IMPORTANT]
> Não exclua a conta se tiver configurado o encaminhamento de email ou se tiver convertido essa conta em uma caixa de correio compartilhada. Ambos precisam da conta para ancorar o encaminhamento ou a caixa de correio compartilhada.

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione o nome do funcionário que você deseja excluir.
3. Em nome do usuário, selecione **Excluir usuário**. Escolha as opções que você deseja para esse usuário e selecione **Excluir usuário**. Se você já tiver dado a outro usuário acesso ao email e ao OneDrive desse usuário, não será preciso fazer isso novamente aqui.

Quando você exclui um usuário, a conta se torna inativa por aproximadamente 30 dias. Você tem até esse prazo para restaurar a conta antes de ela ser permanentemente excluída.
  
## <a name="does-your-organization-use-active-directory"></a>Sua organização usa o Active Directory?

Se sua organização sincroniza contas de usuário Microsoft 365 de um ambiente local do Active Directory, você deve excluir e restaurar essas contas de usuário no serviço local do Active Directory. Não é possível excluí-las ou restaurá-las no Office 365.

Para saber como excluir e restaurar a conta de usuário no Active Directory, consulte [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).
  
Se você estiver usando Azure Active Directory, consulte o cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell.
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>O que você precisa saber sobre o encerramento da sessão de email de um funcionário

Aqui estão as informações sobre como excluir um funcionário do email (Exchange).
  
|||
|:-----|:-----|
|**O que você pode fazer** <br/> |**Como fazer isso** <br/> |
|Encerrar uma sessão (como o Outlook na Web, Outlook, Exchange Active Sync, etc.) e forçar a abertura de uma nova sessão  <br/> |Redefina a senha  <br/> |
|Encerrar uma sessão e bloquear o acesso a sessões futuras (para todos os protocolos)  <br/> |Desabilite a conta. Por exemplo, (no centro de administração Exchange ou usando o PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Encerrar a sessão de um protocolo específico (como ActiveSync)  <br/> |Desabilite o protocolo. Por exemplo, (no centro de administração Exchange ou usando o PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

As operações acima podem ser feitas em três locais:
  
|||
|:-----|:-----|
|**Se você encerrar a sessão aqui** <br/> |**Quanto tempo demora** <br/> |
|No centro de administração do Exchange ou usando o PowerShell  <br/> |O atraso esperado é de 30 minutos  <br/> |
|No centro de administração do Azure Active Directory  <br/> |O atraso esperado é de 60 minutos  <br/> |
|Em um ambiente local  <br/> |O atraso esperado é de três horas ou mais  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a>Como obter a resposta mais rapidamente para o encerramento da conta

 **Mais rápido**: use o centro de administração do Exchange (use o PowerShell) ou o centro de administração do Azure Active Directory. Em um ambiente local, pode demorar várias horas para sincronizar a alteração por meio do DirSync.
  
 **O mais rápido para um usuário com presença local e no Datacenter do Exchange**: Encerre a sessão usando o centro de administração do Azure Active Directory/centro de administração do Exchange e altere TAMBÉM no ambiente local. Caso contrário, a alteração no centro de administração do Azure Active Directory/centro de administração do Exchange será substituída pelo DirSync.
  
## <a name="related-articles"></a>Artigos relacionados

[Restaurar um usuário](restore-user.md)
