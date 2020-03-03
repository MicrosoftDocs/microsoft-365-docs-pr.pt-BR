---
title: Permitir que os membros enviem como ou enviem em nome de um grupo
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Saiba como permitir que os membros enviem email como um grupo do Office 365 ou enviem email em nome de um grupo do Office 365.
ms.openlocfilehash: 0179dbd2e3093ce80929f6c5f9e689aece845a40
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352752"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Permitir que os membros enviem como ou enviem em nome de um grupo

Um membro de um grupo do Office 365 que tenha recebido permissões **Enviar como** ou **enviar em nome** de agora pode enviar emails como o grupo ou em nome do grupo. Este tópico explica como um administrador pode definir essas permissões.
  
Por exemplo, se Megan Bowen fizer parte do grupo **Training** Office 365, e tiver permissões **Send** as no grupo, se ele enviar um email como o grupo, será parecido com o grupo de **treinamento** enviado por email. 
  
A permissão **enviar em nome** de permite que um usuário envie um email em nome de um grupo do Office 365. Por exemplo, se Alex Wilber é parte do grupo **marketing** do Office 365 e tem permissões **de enviar em nome** de e envia um email como grupo, o email parece que foi enviado por **Alex Wilber em nome de marketing**.

> [!IMPORTANT]
> Você pode configurar **Enviar como** ou **enviar em nome** de um determinado usuário, mas não ambos. Se você configurar ambos, o padrão será **Enviar como**.

> [!TIP]
> Confira as etapas em [Enviar email de ou em nome de um grupo do Office 365](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) para saber como usar o Outlook e o Outlook na Web para enviar emails de um grupo.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Permitir que os membros enviem email como um grupo

Esta seção explica como permitir que os usuários enviem emails como um grupo no [centro de administração do Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (Eat) no Exchange Online.
  
1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administração do Exchange</a>, vá para **grupos**de **destinatários** \> .
    
2. Selecione **Editar**![ícone](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) de grupo no grupo para o qual você deseja permitir que os usuários enviem.   
    
3. Selecione **delegação de grupo**.
    
4. Na seção **Enviar como** , selecione o **+** sinal para adicionar os usuários que você deseja enviar como o grupo. 
    
    ![Selecione o sinal de adição para adicionar os usuários que você deseja enviar como o grupo do Office 365](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Digite para pesquisar ou selecionar um usuário da lista. Selecione **OK** e **salvar**.
    
    ![Digite para pesquisar ou selecionar um usuário na lista](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Permitir que os membros enviem email em nome de um grupo

Esta seção explica como permitir que os usuários enviem emails em nome de um grupo no centro de administração do Exchange (Eat) no Exchange Online.
  
1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administração do Exchange</a>, vá para **grupos**de **destinatários** \> .
    
2. Selecione **Editar** ![ícone](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) de grupo no grupo para o qual você deseja permitir que os usuários enviem. 
    
3. Selecione **delegação de grupo**.
    
4. Na seção enviar em nome de, selecione o **+** sinal para adicionar os usuários que você deseja enviar como o grupo. 
    
    ![Selecione o sinal de adição para adicionar os usuários que você deseja enviar como o grupo do Office 365](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Digite para pesquisar ou selecionar um usuário da lista. Selecione **OK** e **salvar**.
    
    ![Digite para pesquisar ou selecionar um usuário na lista](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Artigos relacionados

[Saiba mais sobre grupos do Office 365](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Conjunto-unificado](https://go.microsoft.com/fwlink/p/?LinkId=616189)
