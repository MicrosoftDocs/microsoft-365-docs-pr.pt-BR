---
title: Permitir que os membros enviem como ou enviem em nome de um grupo
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Saiba como permitir que os membros do grupo enviem emails como um grupo do Microsoft 365 ou enviem emails em nome de um grupo do Microsoft 365.
ms.openlocfilehash: 44a0a7a690c8faa9fe00732e8154f36aa5a6fe6f
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727074"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Permitir que os membros enviem como ou enviem em nome de um grupo

Um membro de um grupo do Microsoft 365  que recebeu permissões **Enviar** como ou Enviar em nome pode enviar emails como o grupo ou em nome do grupo. (Os convidados no grupo não podem receber essas permissões.)

Este artigo explica como um administrador global ou do Exchange pode definir essas permissões.
  
Por exemplo, se Megan Bowen faz parte do grupo Treinamento do **Microsoft** 365 e tem **Send** como permissões no  grupo, se ela enviar um email como o grupo, ele será parecido com o grupo de treinamento enviado pelo email. 
  
A **permissão Enviar em Nome** permite que um usuário envie emails em nome de um grupo do Microsoft 365. Por exemplo, se Alex Wilber faz parte do grupo **marketing** do Microsoft 365 e tem permissões **Enviar** em Nome e envia um email como o grupo, o email parece ter sido enviado por **Alex Wilber** em nome do Marketing .

> [!IMPORTANT]
> Você pode configurar **Enviar como** ou Enviar **em nome** de um determinado usuário, mas não ambos. Se você configurar ambos, ele será padrão **para Enviar como**.

> [!TIP]
> Consulte Enviar emails de ou em nome de um grupo do [Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) para saber como usar o Outlook e o Outlook na Web para enviar emails de um grupo.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Permitir que os membros enviem emails como um grupo

Esta seção explica como permitir que os usuários enviem emails como um grupo no Centro de administração do [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) no Exchange Online.
  
1. No Centro <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">de administração do Exchange,</a>vá para **Grupos de** \> **Destinatários**.
    
2. Selecione **Editar** ![ Editar ícone do grupo no grupo que você deseja permitir que os ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) usuários enviem como.   
    
3. Selecione **delegação de grupo**.
    
4. Na seção **Enviar como,** selecione o **+** sinal para adicionar os usuários que você deseja enviar como o Grupo. 
    
    ![Captura de tela da caixa de diálogo enviar como](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Digite para pesquisar ou escolher um usuário na lista. Selecione **OK** e **Salvar**.
    
    ![Digite para pesquisar ou escolher um usuário na lista](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Permitir que os membros enviem emails em nome de um grupo

Esta seção explica como permitir que os usuários enviem emails em nome de um grupo no Centro de administração do Exchange (EAC) no Exchange Online.
  
1. No Centro <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">de administração do Exchange,</a>vá para **Grupos de** \> **Destinatários**.
    
2. Selecione **Editar** ![ Editar ícone do grupo no grupo que você deseja permitir que os ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) usuários enviem como. 
    
3. Selecione **delegação de grupo**.
    
4. Na seção Enviar em Nome, selecione o sinal para adicionar **+** os usuários que você deseja enviar como o Grupo. 
    
    ![Captura de tela de envio em nome da caixa de diálogo](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Digite para pesquisar ou escolher um usuário na lista. Selecione **OK** e **Salvar**.
    
    ![Digite para pesquisar ou escolher um usuário na lista](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Artigos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Saiba mais sobre grupos do Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
